# HAMUGANGgames Firebase setup

1. Firebase Console → Authentication → Sign-in method → Email/Password: ON.
2. Optional but recommended: Authentication → Sign-in method → Anonymous: ON. This enables username lookup and guest sessions. If Anonymous is OFF, users can still use Email/Password login and online rooms after login.
3. Realtime Database → Rules: paste `database.rules.json` and Publish.
4. Project Settings → Your apps → Web app: keep the Firebase config already in `index.html`.
5. Deploy the repository to GitHub/Vercel.
6. Test: register on Device A, then use the SAME EMAIL + PASSWORD on Device B. Username login requires Anonymous Auth to be enabled because the username→email lookup is protected by the database rules.

The web config is not a service-account secret. Never put a Firebase service-account private key in this HTML.
