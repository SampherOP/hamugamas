# HAMUGANGgames Firebase setup

This build already contains your Firebase Web App configuration.

Project: hamuganggames
Realtime Database: https://hamuganggames-default-rtdb.asia-southeast1.firebasedatabase.app

## Firebase Console
1. Authentication -> Sign-in method -> Email/Password -> Enabled.
2. Authentication -> Sign-in method -> Anonymous -> Enabled (required for guest multiplayer).
3. Realtime Database -> create the database in your selected region.
4. Realtime Database -> Rules: paste `database.rules.json` and Publish.
5. Authentication -> Settings -> Authorized domains: add your Vercel domain (for example `hamuganggames.vercel.app`).

## Deploy
Upload this folder to GitHub and import the repository into Vercel. The site is a static HTML app; no Node/Python backend is required for the Firebase features.

## Important
The Firebase Web API key is a public web-app identifier. Database access is protected by Firebase Authentication and Realtime Database Rules. Never put a Firebase service-account private key in this website.
