HAMUGANGgames - A to Z Firebase Fix V3

FILES
- index.html: patched single-file portal. Firebase config is already present.
- database.rules.json: MUST be published to Firebase Realtime Database -> Rules.

IMPORTANT
GitHub/Vercel does NOT automatically publish database.rules.json to Firebase.

FIREBASE
1. Firebase Console -> HAMUGANGgames project.
2. Build -> Realtime Database -> Rules.
3. Replace the existing rules with the contents of database.rules.json.
4. Click Publish.
5. Authentication -> Sign-in method: Email/Password ON. Anonymous ON (needed for username lookup / room directory before login).
6. Redeploy Vercel / refresh with Ctrl+Shift+R.

DATA PATHS USED BY THIS VERSION
users/{uid}
publicUsers/{uid}
usernames/{usernameKey}
hostRooms/{uid}
rooms/{roomCode}
roomPlayers/{roomCode}/{uid}/{browserConnectionId}
roomChat/{roomCode}/{messageId}
roomReactions/{roomCode}/{reaction}/{uid}
votes/{PakistanVotingCycle}/{uid}

MULTIPLAYER
- One hosted room per Firebase account using hostRooms transaction.
- Custom HAMU-1234 join reads rooms/{code} directly.
- Player presence is stored outside room metadata, so chat/player writes are not blocked by room-owner rules.
- Chat is shared through roomChat/{code}.
- Player count is calculated from unique Firebase UIDs.
- Host disconnect is marked with onDisconnect and room is hidden/cleaned after 10 seconds by connected clients.

VOTES
- One vote per Firebase UID per Pakistan 4:00 AM voting cycle.
- A vote is stored at votes/{cycle}/{uid}.
- All authenticated clients read the whole cycle, so totals are shared across devices.
- Clicking the same game removes the vote; clicking another game moves the vote.

AUTH / PROGRESS
- Firebase Authentication is the identity source.
- Profile/progress/favorites/points/streak are stored at users/{uid}.
- The browser localStorage is only a cache.
