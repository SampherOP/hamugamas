# HAMUGANGgames — Multiplayer Permission Fix

The site uses Firebase Authentication and Realtime Database. If Login/Register works but **Create Live Server** says `permission_denied`, the problem is almost always that the Realtime Database rules in the Firebase Console are still in Locked mode or the updated rules were not published.

## Publish the rules

1. Open Firebase Console and select **hamuganggames**.
2. Go to **Build → Realtime Database**.
3. Open the **Rules** tab.
4. Replace the existing rules with the contents of `database.rules.json` from this project.
5. Click **Publish**.
6. Refresh the HAMUGANGgames Vercel site with `Ctrl + Shift + R`.
7. Login again if necessary and test **Create Live Server**.

GitHub/Vercel does **not** automatically deploy Realtime Database Security Rules. The rules live on Firebase's servers and must be published there (or deployed with Firebase CLI).

The updated `index.html` also shows a specific Firebase permission message instead of hiding `PERMISSION_DENIED` behind a generic room-creation error.
