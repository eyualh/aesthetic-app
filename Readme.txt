AESTHETIC FURNITURE - ANDROID APP (APK) BUILD KIT
==================================================

What this is
------------
Everything needed to turn the workshop app into an Android app file (APK).
The APK installs on any Android phone or tablet. It works fully offline.

IMPORTANT - what the APK version is and is not
  * It keeps its data ON THAT PHONE ONLY. It does NOT sync with the web
    link or your PC, and it has no "owner-only" protection (the password
    lock still works).
  * To move data between the APK and the web app, use
    Settings > Backup & restore (the backup file can be shared by
    WhatsApp / email / Google Drive).
  * Invoices, reports and backups open the phone's "Share" menu, so you
    can save them, send them on WhatsApp, or open them in Chrome to print.
  * If you want the SAME data on phone and PC, keep using the web link.
  * This is a "debug" APK for installing directly. It is NOT a Play Store
    release (that needs a signing key - ask a developer or me).
  * This kit was prepared without being able to run the build here.
    The app code was tested; the build steps below follow the standard
    Capacitor method but have not been run end to end. If a step fails,
    copy the error message and send it to me.


OPTION A - build online, nothing to install (recommended)
---------------------------------------------------------
1. Make a free account at github.com and create a NEW repository
   (choose "Private").
2. Upload ALL files from this folder into the repository:
   "Add file" > "Upload files" > drag everything in.
   Tip: some computers hide the folder named ".github". If it does not
   upload, instead choose "Add file" > "Create new file", type the name
       .github/workflows/build-apk.yml
   and paste in the text of the file "build-apk.yml.txt".
3. Open the "Actions" tab. If asked, click "I understand, enable".
   Choose "Build APK" on the left, then "Run workflow".
4. Wait about 5-10 minutes until it shows a green tick.
5. Open the finished run, scroll to "Artifacts", download
   "aesthetic-furniture-apk" (a zip). Unzip it: you get app-debug.apk.
6. Send app-debug.apk to your phone (WhatsApp, Telegram, email, USB).
   Tap it to install. If Android asks, allow "Install unknown apps" for
   the app you opened it from.


OPTION B - build on a computer with Android Studio
--------------------------------------------------
1. Install Node.js (20 or newer) and Android Studio.
2. Open a terminal in this folder and run:
       npm install
       npx cap add android
       npx @capacitor/assets generate --android
       npx cap sync android
       npx cap open android
3. In Android Studio: Build > Build Bundle(s) / APK(s) > Build APK(s).
4. The file is in android/app/build/outputs/apk/debug/app-debug.apk


OPTION C - installable website instead of an APK
------------------------------------------------
The earlier "Workshop_App_Phone_Install.zip" can be put on any https web
host, then installed from Chrome (menu > Install app). It behaves like an
app but is not an APK file.


Changing the app later
----------------------
When the app is updated, replace www/index.html with the new version and
build again. Installing the new APK over the old one keeps the phone's data
as long as the app id stays the same (com.aestheticfurniture.workshop).
Always download a backup first.
