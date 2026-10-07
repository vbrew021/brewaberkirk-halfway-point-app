# BrewAberKirk Halfway Point App: GitHub Pages + live family picks

GitHub hosts the website for free. Google's Firebase stores the shared picks
on its free plan, which needs no credit card and easily covers a family.
Your family won't need any accounts; they just open the link and enter the
family code once.

Do these steps on a computer. It takes about 20 minutes.

## 1. Put the site on GitHub Pages

1. Unzip this file. You'll get `index.html`, `firebase-config.js`,
   `firestore.rules` and this guide.
2. Sign in to github.com and create a **New repository**. Name it
   `brewaberkirk-halfway-point` and choose **Public** (free GitHub Pages
   needs a public repository). Click **Create repository**.
3. Click **uploading an existing file**, drag in all four files, and click
   **Commit changes**.
4. Go to the repository's **Settings**, then **Pages**. Under **Build and
   deployment**, set Source to **Deploy from a branch**, Branch to **main**
   and folder to **/ (root)**, then **Save**.
5. After a minute or two, your site appears at
   `https://YOUR-GITHUB-NAME.github.io/brewaberkirk-halfway-point/`.

At this point everything works except the live family list.

## 2. Create the free Firebase database

1. Go to console.firebase.google.com and sign in with a Google account.
2. Click **Create a project**, name it `brewaberkirk-halfway`, and turn off
   Google Analytics (not needed). Finish creating it.
3. In the left menu, open **Build**, then **Firestore Database**, then
   **Create database**. Pick the location closest to you (any US location is
   fine) and choose **Start in production mode**.
4. Open the **Rules** tab. Delete what's there and paste in everything from
   `firestore.rules`. Replace `YOUR-FAMILY-CODE` in both places with the code
   your family will use, such as a word plus a number, keeping the single
   quotes. Click **Publish**.

The family code lives only in these rules, so it never appears on the public
website or on GitHub. Anyone without the code can't see or change your picks.

## 3. Connect the site to Firebase

1. In Firebase, click the gear next to **Project overview**, then
   **Project settings**.
2. Under **Your apps**, click the web icon (**</>**). Give it a nickname like
   `halfway-site`. Leave Firebase Hosting unchecked. Click **Register app**.
3. Firebase shows a block of code containing `const firebaseConfig = { ... }`.
   Keep that page open.
4. On GitHub, open `firebase-config.js` in your repository and click the
   pencil icon to edit it.
5. Replace each `PASTE_...` value with the matching value from Firebase
   (`apiKey`, `authDomain`, `projectId`, `storageBucket`,
   `messagingSenderId`, `appId`). Keep the quotes. Click **Commit changes**.

These Firebase values are designed to be public; the family code in your
security rules is what protects the list.

## 4. Use it

1. Open your GitHub Pages address. In **Our picks**, enter the family code and
   tap **Connect**. Each device only needs to do this once.
2. Send the link and the code to the family. Stars from Brew, Aber and Kirk
   appear for everyone instantly. Picks someone already starred on their own
   device are added the first time they connect.

To change the family code later, edit the rules in Firebase and publish
them. Everyone will be asked for the new code, and picks saved under the
old code won't carry over.

## Updating the app later

When Claude gives you a new version, upload the new `index.html` to the
repository (**Add file**, then **Upload files**) and commit. GitHub Pages
updates within a few minutes. Don't replace `firebase-config.js` unless you
mean to; your picks are stored in Firebase and aren't affected by updates.
