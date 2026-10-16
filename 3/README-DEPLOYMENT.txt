MATHCLOUD JAMB — REPAIRED FLAT DEPLOYMENT PACKAGE
================================================

This package keeps the single-folder/root deployment layout from the modified archive.

WHAT WAS CHECKED
- All HTML pages and local asset/script references in the root package.
- JavaScript syntax in every standalone .js file.
- Inline JavaScript syntax embedded in all HTML pages.
- Manifest icon paths.
- Restored firebase-database.rules.json, which existed in the known-good archive but was missing from the flattened archive.
- Updated service-worker cache version so browsers do not keep stale pre-fix files.
- Improved sign-in errors so Firebase domain/auth/network errors are visible instead of being reported as a generic failure.
- Improved notices: errors and warnings remain visible until replaced; success/info notices dismiss after 9 seconds.

DEPLOYMENT
1. Extract this ZIP.
2. Deploy the CONTENTS of this folder as the Vercel project root (do not deploy an extra enclosing folder).
3. In Firebase Console > Authentication > Settings > Authorized domains, confirm your exact deployed Vercel hostname is listed.
4. Confirm Email/Password and Google providers are enabled under Firebase Authentication > Sign-in method.
5. In Firebase Realtime Database, confirm the database URL in firebase-config.js matches the database for project school-37083.
6. Review firebase-database.rules.json and deploy the rules from Firebase Console only if they match your intended access policy. Do not loosen rules just to make content appear.
7. Test sign-in, registration, topic loading, practice, mock submission and admin access on the deployed HTTPS URL. Clear the site's cached data/service worker once after the first deployment if the browser still shows an old version.

IMPORTANT LIMITATION
Static code checks cannot sign in to your private Firebase project or verify its live database rules/data. If sign-in still fails, the page now displays the Firebase error code. `auth/unauthorized-domain` means the deployed hostname must be added in Firebase Authentication Authorized domains. Permission-denied/database errors require checking the deployed Realtime Database rules and the affected data paths.

The Firebase web config is public client configuration; security must be enforced by Firebase Authentication and Realtime Database Rules. Never put service-account keys or private credentials in this folder.
