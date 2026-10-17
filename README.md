# LiveWaveTv Android APK project

This project wraps the uploaded `index.html` in a Capacitor Android app. The workflow builds a **debug APK** using GitHub Actions, so you do not need a computer or Android Studio.

## Important
- This ZIP is the project source, **not an already-built APK**. The APK is produced after you upload the project to GitHub and run the workflow.
- Live TV playback needs an internet connection. Your page loads HLS.js and Google Fonts from online CDNs, and the channel streams must remain available.
- This is a debug APK for testing/personal installation, not a signed release APK for Google Play.

## Steps using only an Android phone

1. Download and extract this ZIP with your phone's Files app.
2. Sign in at https://github.com/ and create a **new public repository** named `LiveWaveTv-Android`. Do not add a README or license during repository creation.
3. Open the new empty repository in Chrome. Use **Add file → Upload files**.
4. In your phone's file picker, open the extracted `LiveWaveTv-Android` folder. Upload the project contents, including the `.github` folder and `www` folder. If your file picker hides dot-folders, use a file manager that shows hidden files. Keep the folder structure exactly as it is.
5. Commit the uploaded files to the `main` branch.
6. In the repository, open the **Actions** tab. If GitHub asks to enable workflows, enable them.
7. Select **Build LiveWaveTv APK** and tap **Run workflow** → **Run workflow**.
8. Wait for the workflow to finish with a green check. Open that successful run and scroll to **Artifacts**.
9. Tap `LiveWaveTv-debug-APK` to download the artifact ZIP. Extract it; inside is `app-debug.apk`.
10. Tap `app-debug.apk` and allow your phone to install apps from that browser/file manager if Android asks. Only install an APK you built from the repository you control.

## If the build fails
Open the failed run, tap the failed step, and copy the error text. Send it to ChatGPT so the workflow can be corrected.

## Updating the app later
Replace `www/index.html` with your updated website file in GitHub and commit. The workflow runs again and produces a new APK artifact. Android may treat updates as a different app if the package ID changes; keep `com.princehacker.livewavetv` unchanged.
