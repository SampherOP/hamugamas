# Important Firebase Console step

The `database.rules.json` file in GitHub does NOT automatically publish rules to Firebase.

Open Firebase Console → Realtime Database → Rules, replace the rules with the contents of `database.rules.json`, then click **Publish**.

The site now initializes Firebase Database independently of Anonymous Auth. Therefore, if Anonymous Auth is disabled, Email/Password login and multiplayer for signed-in users still work. Enable Anonymous Auth if you want username-login lookup and guest sessions.
