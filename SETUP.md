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
   `firestore.rules`. Replace `YOUR-FAMILY-CODE` on the line near the top with the
   code your family will use, such as a word plus a number, keeping the single
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

## Adding your own destinations and suggestions

- **Destinations:** under the city buttons, tap **+ Add a destination**, type a
  town (adding the state helps, like `Branson, MO`), and tap the right match.
  It appears on both maps with a dashed purple ring, and gets directions,
  flight searches, lodging searches and trip costs like the other cities.
- **Activities, hidden gems, restaurants and places to stay:** at the bottom of each list,
  tap **+ Suggest...**. Pasting a Google Maps link is optional but helpful:
  the name then opens that exact place, and full-length links fill in the
  name for you. Family suggestions are outlined in dashed purple and labeled
  with who added them. Anyone can star or remove them.
- **Getting descriptions written:** tap **Copy suggestions for Claude** in
  **Our picks**, paste the list into a chat with Claude, and ask for
  descriptions and tags. Claude can fold them into the built-in lists in the
  next `index.html`.

The app asks which family is adding something, so additions are labeled.
To remove anything the family added, use the **Remove** button next to it,
or the **Family additions** section at the bottom of the page, which lists
everything in one place.

## Travel dates and weather

Suggest date ranges in **Travel dates** with **+ Suggest dates**; each family
answers Works, Maybe or Can't, and **Use these dates** makes one official.
You can also set the trip dates directly. Dates are shared with the whole
family once you're connected, and the
**Weather** section shows the forecast (within about 16 days) and typical
weather for those dates in the selected city.

## Voting and the trip plan

- **Family vote:** open a city, then choose your family's 1st, 2nd or 3rd
  choice in its directions panel. Standings appear in **Family vote**.
- **Trip calendar:** in **Our trip** at the top, once travel dates are set,
  each city gets a small calendar of your trip. Tap a day to open it, then add activities, plan breakfast, lunch and dinner, mark travel days and add
  notes. **Add to calendar** downloads a file your calendar app can open.

## Updating the app later

When Claude gives you a new version, upload the new `index.html` to the
repository (**Add file**, then **Upload files**) and commit. GitHub Pages
updates within a few minutes. If the new version comes with an updated
`firestore.rules`, also paste it into Firebase's **Rules** tab (with your family code
filled in on the line near the top) and click **Publish**. Don't replace `firebase-config.js` unless you
mean to; your picks are stored in Firebase and aren't affected by updates.

## Updating your Firebase rules (needed for family suggestions)

If you set up Firebase before family suggestions were added, update the rules
once so suggestions can sync:

1. In Firebase, open **Firestore Database**, then the **Rules** tab.
2. Replace everything with the new `firestore.rules` file, change
   `YOUR-FAMILY-CODE` in all four places to your family code, and click
   **Publish**.

Until you do, starred picks still sync, but new suggestions only appear on the
device where they were added.
