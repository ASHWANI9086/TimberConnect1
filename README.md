# TimberConnect
Kotlin Android shell + web app in `app/src/main/assets/index.html`.

## 1. Run
Android Studio > Open this folder > wait for Gradle sync > Run.

## 2. Make buy & sell REAL (shared listings) - 5 minutes, free
1. console.firebase.google.com > Add project > Build > Firestore Database > Create (production mode).
2. Firestore > Rules > paste the contents of `firestore.rules` > Publish.
3. Project settings > General > Your apps > add a Web app > copy `projectId` and `apiKey`.
4. Open `app/src/main/assets/index.html`, find `const CFG={pid:'',key:''}` and fill both values.
5. Run again. Listings made in Sell now appear for every user. Without these values the app still works, but listings stay on one phone.

## 3. GitHub
git init && git add . && git commit -m "TimberConnect" && git branch -M main
git remote add origin https://github.com/<you>/TimberConnect.git && git push -u origin main
Every push builds a debug APK (Actions > Artifacts).

## 4. Play Store
1. Change `applicationId` in `app/build.gradle.kts` to your own unique id.
2. Build > Generate Signed App Bundle > Android App Bundle (create and KEEP the keystore safe).
3. Play Console: create app > upload the .aab > fill Data safety (listings you post include name, phone, address, shown publicly) > add a privacy policy URL > screenshots > submit for review.
4. Replace the launcher icon via File > New > Image Asset if you want.
