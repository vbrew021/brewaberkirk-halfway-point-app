# BrewAberKirk Halfway Point App: guidelines for Claude

Paste this file at the start of a new chat about the app, along with the
current `index.html` and `firestore.rules` if changes are needed.

## What the app is

A single-page website that helps three related families find a fair place to
meet in the middle and plan the trip together.

- **Brew:** 2 adults (41 and 36), kids 10 and 8, sometimes their adult child
  (19). Michigan; usually travels with the Kirks from Detroit, sometimes
  Grand Rapids.
- **Kirk:** 2 adults (68 and 65), the grandparents. Michigan, with the Brews.
- **Aber:** 2 adults (44 and 39), child 5. Texas.

Two trip types: driving (Spring Lake, MI and Andice, TX) and flying
(Detroit, MI and Austin, TX). The map shows the line of points equally far
from both, with suggested cities near it.

## How it's hosted

- **GitHub Pages** (personal account, public repository) serves the files:
  `index.html`, `firebase-config.js`, `firestore.rules` (reference copy),
  `SETUP.md`, `CHANGELOG.md` and this file.
- **Firebase Firestore** (free Spark plan) stores shared family data under
  `halfway/{familyCode}/...`. The family code appears only in the Firebase
  security rules, on one line near the top (`function isFamily(code)`).
- `index.html` is fully self-contained: map data, libraries, city lists and a
  built-in list of about 21,000 US towns are inlined. Only Firebase, weather
  and optional place-lookup services are loaded from the web.
- A copy is also published as a Claude artifact; the live family list, place
  lookups and weather only work on the GitHub site.

## Conventions to follow on every change

1. **How-to text under every heading.** Each section gets a short, plain
   description directly below its heading (class `sec-help`) explaining what
   to tap. Add one for any new section and update existing ones when a change
   makes them out of date.
2. **Semantic versioning.** MAJOR for changes that need setup redone or would
   lose saved data; MINOR for new features; PATCH for fixes. Update the
   version label at the bottom of the page ("Version X.Y.Z · date") and add a
   `CHANGELOG.md` entry every time.
3. **Say whether Firebase rules change.** If new shared data is saved, update
   `firestore.rules`, keep the family code on its single line, mention it in
   the changelog entry ("Needs updated Firebase rules") and tell the user.
4. **Family additions look different.** Anything a family member adds
   (destinations, suggestions) uses the dashed purple style and is labeled
   with who added it. Everything added can be removed, with a confirmation.
5. **Family labels.** The "I'm with" chooser in the top bar sets the family
   for the device. Picks, votes, suggestions, dates and plan edits are labeled
   Brew, Aber or Kirk. If no family is chosen, offer the three family buttons
   inline or point to "I'm with" rather than sending people elsewhere.
6. **Stay honest about built-in content.** Built-in activities, hidden gems,
   restaurants and lodging come from Claude's knowledge; only list places
   Claude is confident still exist, and leave gaps rather than guess.
   Periodic freshness checks happen in chat with web search.
7. **Work offline-first and degrade gracefully.** Some services (Open-Meteo)
   are blocked on the user's network. Keep fallbacks (NWS for forecasts, NASA
   POWER for typical weather, built-in town list for search), short timeouts,
   clear error messages with a Details note and a Try again button.
8. **Design and accessibility.** Mobile-first; tap targets at least 44px;
   light and dark mode via CSS color tokens; visible focus outlines; labels
   on every input; popups use `<dialog>`; keep long features compact (for
   example, the trip plan is a small calendar that opens a day popup).
9. **No browser storage for shared data.** `localStorage` is only a
   per-device fallback and cache; shared data lives in Firestore.
10. **Collapsible sections.** Every section is a `<section>` with an `id`
    placed directly in `<main>`, with its heading first and the how-to text
    right after. A script adds the Hide/Show button automatically; sections
    start expanded and each device remembers what was hidden. New sections
    must follow this structure and get a menu link.
11. **Update everywhere.** Each release updates `index.html`, the Claude
    artifact and `CHANGELOG.md`, and `SETUP.md` when instructions change.
    Remind the user to upload to GitHub and check the version label.

## Page order (top to bottom)

Top bar: menu button, app name (links home), "I'm with" family chooser, How
this works. Then Trip at a glance, followed by two steps.

**Step 1: Decide where and when.** Trip-type toggle, Map, Choose a meeting
city (with + Add a destination), Getting there (directions or flight cards
and vote buttons), Who's traveling, Family vote, Travel dates (trip dates and
suggested dates), Weather (with packing hints), Trip cost (with Who pays
what).

**Step 2: Plan the trip.** Places to stay, Filter things to do, Indoor,
Outdoor, Hidden gems, Places to eat, Our picks, Trip plan (calendar with day
popups), To-do list, Family additions, version label.

The menu also holds Expand all, Collapse all, Larger text, Print trip
summary and Download a backup.

## Shared data (Firestore collections under halfway/{code}/)

`picks`, `custom` (suggestions: sections in, out, gem, eat, stay), `places`
(added destinations), `trip` (official travel dates), `dateOpts` (suggested
date ranges with each family's Works/Maybe/Can't answer), `votes` (one
document per family, ranked top three cities), `plan` (one document per city
and day), `todos` (task, who's on it, done).
