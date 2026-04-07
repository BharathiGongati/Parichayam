# Parichayam

Parichayam is a Firebase-powered matrimony platform built for Arya Vyshya families across Andhra Pradesh and Telangana.

This repository includes the public website, member dashboard, admin panel, staff tools, and Firebase backend needed to run the project.

## What Is In This Repo

- `index.html`: public landing page
- `auth.html`: sign-up and sign-in flow
- `dashboard.html`: member dashboard
- `admin.html`: super admin panel
- `agent.html`: agent workflow
- `matchmaker.html`: matchmaker workflow
- `checkout.html`: payment and checkout flow
- `functions/`: Firebase Cloud Functions backend
- `firestore.rules`: Firestore security rules
- `storage.rules`: Firebase Storage security rules
- `firebase.json`: Hosting and Firebase deployment config
- `docs/`: owner SOPs, training material, and project notes

## Stack

- Firebase Hosting
- Firestore
- Firebase Storage
- Firebase Authentication
- Firebase Cloud Functions
- Static HTML, CSS, and JavaScript frontend

## Local Setup

1. Copy `.firebaserc.example` to `.firebaserc` and set your Firebase project id.
2. Open `parichayam-firebase-config.js` and paste your Firebase web app config.
3. Create `functions/.env` from `functions/.env.example` and fill in only server-side secrets.
4. Install backend dependencies:

```powershell
cd functions
npm install
```

5. Start Firebase emulators or deploy selectively as needed.

## First Admin Setup

1. Register one account from `auth.html`.
2. Open Firestore in Firebase Console.
3. Find that user in `members/{uid}`.
4. Change `role` to `ADMIN`.

## Deploy

Deploy rules first:

```powershell
firebase deploy --only firestore:rules,storage
```

Deploy hosting:

```powershell
firebase deploy --only hosting
```

Deploy functions:

```powershell
firebase deploy --only functions
```

## Important Security Notes

- Do not commit `functions/.env`.
- Keep payment keys, OTP provider credentials, and other secrets server-side only.
- Review `firestore.rules` and `storage.rules` before every production launch.
- Test admin, verification, and payment flows in a non-production Firebase project first.

## Current Repo Conventions

- `main` is the primary branch.
- Use short feature branches for changes before merging back to `main`.
- Keep local Firebase cache folders, logs, and `node_modules` out of Git.

## Related Project Notes

- Firebase setup reference: [FIREBASE-SETUP.md](./FIREBASE-SETUP.md)
- Operational and training documents: [docs/](./docs)
