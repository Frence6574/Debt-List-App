# Fix Firebase Admin SDK Credential Issue

## Steps to Resolve Invalid JWT Signature Error

1. **Regenerate Service Account Key**
   - Go to https://console.firebase.google.com/project/test-debt-63eb7/settings/serviceaccounts/adminsdk
   - Click on the service account (likely "firebase-adminsdk-...@test-debt-63eb7.iam.gserviceaccount.com")
   - Click "Keys" tab
   - Click "Add Key" > "Create new key"
   - Choose JSON format
   - Download the new key file

2. **Replace the Old Key File**
   - Rename the downloaded file to `serviceAccountKey.json`
   - Replace the existing `serviceAccountKey.json` in the project root with the new file

3. **Verify the Fix**
   - Restart the server
   - Test the user creation endpoint to ensure it works

## Current Status
- [x] Step 1: Regenerate key in Firebase Console (completed - new key with private_key_id: bb581ede93e33a408719785ff6ed1a024aa9f596)
- [x] Step 2: Replace serviceAccountKey.json (completed - file updated with new key)
- [x] Step 3: Test user creation (SUCCESS - user created successfully with UID: 0CMp1SMG6IdwFplyGqQ40ZZDCl92)

## Issue Resolution
- The Firebase Admin SDK credential issue has been resolved
- The new service account key is valid and working correctly
- User creation endpoint is now functioning properly
- Server is running successfully on port 3000

## Summary
The invalid JWT signature error was caused by an expired or revoked service account key. By regenerating a new key in the Firebase Console and updating the serviceAccountKey.json file, the authentication now works correctly.
