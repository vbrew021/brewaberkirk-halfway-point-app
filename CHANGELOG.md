# BrewAberKirk Halfway Point App: changelog

Versions follow semantic versioning (MAJOR.MINOR.PATCH):

- **MAJOR** goes up for changes that need you to redo setup or that would
  lose saved data.
- **MINOR** goes up for new features. These sometimes need updated Firebase
  rules; the entry will say so.
- **PATCH** goes up for fixes and small adjustments.

The version number is shown at the bottom of the app.

## 1.12.0 (October 8, 2026)
- Changed: the trip toggle, map and city buttons are back at the top, with
  Our trip beside them on a computer (left: map and cities; right: Our trip
  with Overview, Calendar and To-dos tabs). On a phone they stack, map
  first. The page is a little wider on large screens.
- Changed: the trip calendar and to-dos use tabs on every screen size and
  fit the narrower column automatically.
- Improved: on phones, the top bar shows a shorter app name so it isn't cut
  off, and the driving/flying toggle buttons are equal width.

## 1.11.1 (October 8, 2026)
- Added: Hide/Show button on the To-do list. When hidden it shows how many
  tasks are still open; each device remembers the choice, and opening the
  to-do list from Overview or the menu shows it again.

## 1.11.0 (October 8, 2026)
- Changed: Trip at a glance is now Our trip, a dashboard with the overview,
  the trip calendar and the to-do list. On a computer all three show at
  once (calendar and to-dos side by side); on a phone they're tabs, with
  counts, and each device remembers the last tab.
- Changed: the trip calendar and to-do list moved out of Step 2 into Our
  trip. Overview tiles and menu links open the right tab.

## 1.10.0 (October 8, 2026)
- Changed: the page is organized into Step 1 (Decide where and when) and
  Step 2 (Plan the trip). Family vote, Trip cost and Places to stay moved
  up; Our picks and Trip plan now come after the lists you pick from. The
  menu is grouped the same way.
- Changed: "I'm with" (Brew, Aber or Kirk) moved to the top bar and is set
  once per device.
- Added: Trip at a glance, a summary of the leading city, dates, typical
  weather, estimated cost, plan progress and to-dos, with Print trip summary.
- Added: shared To-do list with who's on each task and a starter list.
- Added: printable trip summary in large, easy-to-read type.
- Added: Larger text option and Download a backup in the menu.
- Needs updated Firebase rules (to-do list).

## 1.9.0 (October 8, 2026)
- Added: every section can be collapsed with the Hide/Show button next to its
  title. Sections start expanded; each device remembers what you hide, and
  jumping to a section from the menu opens it.
- Added: Expand all and Collapse all at the bottom of the menu.
- Changed: the map and the city and Getting there areas are now their own
  sections, and the map title sits above the town names.

## 1.8.0 (October 8, 2026)
- Added: Suggested dates in Travel dates. Anyone can suggest a date range
  with an optional note; each family answers Works, Maybe or Can't; the best
  option is marked Top choice and shows typical weather for the selected
  city. Use these dates makes a suggestion the official trip dates.
- Needs updated Firebase rules (suggested dates).

## 1.7.2 (October 8, 2026)
- Added: a short how-to under every section heading explaining what to tap.
- Added: a Getting there heading above the directions and flight cards
  (the menu link is renamed to match).

## 1.7.1 (October 8, 2026)
- Changed: the trip plan is now a compact calendar. Tap a day to plan it in
  a popup, with arrows to move between days. Day tiles show the first
  activity, which meals are planned, and travel days.
- Changed: the app name at the top only highlights its own text and is now a
  link back to the top of the page, which also refreshes it.

## 1.7.0 (October 8, 2026)
- Added: Family vote. Each family ranks its top three cities (3, 2 and 1
  points) from any city's directions panel, and the standings show the
  leader and who still needs to vote.
- Added: Trip plan, a day-by-day plan for your dates in each city, with
  activities, breakfast, lunch and dinner (eat out at a listed restaurant or
  a cook-at-home idea) and notes. Travel days are highlighted, with the first
  and last days marked automatically. Includes Map this day, Add to calendar
  and Copy plan as text.
- Added: Who pays what, splitting gas, flights and lodging by family.
- Added: Packing hints in the Weather section, based on your dates.
- Needs updated Firebase rules (votes and trip plan).

## 1.6.1 (October 8, 2026)
- Faster weather: each device remembers which weather services work and
  goes to them first, gives up on an unresponsive service after about 4
  seconds, shows the forecast as soon as it arrives while typical weather
  fills in, and saves results on the device (forecast for 3 hours, typical
  weather for 30 days) so revisiting a city is instant.

## 1.6.0 (October 8, 2026)
- Added: more named places to stay (now up to 5 per city), including water
  park resorts, historic hotels and lodges near the parks.
- Added: ready-made lodging searches for every city (indoor pools, suites
  that sleep 6, free breakfast, near a top attraction, cabins and lodges),
  so each city shows 5 to 10 options.

## 1.5.2 (October 8, 2026)
- Fixed: typical weather now falls back to NASA's free POWER climate data
  when Open-Meteo can't be reached, and the forecast notes its source.
- Added: a Details note and a Try again button when weather can't load, to
  show which weather service was blocked.

## 1.5.1 (October 8, 2026)
- Fixed: typical weather often failed to load. It now requests only your
  trip dates for each past year, retries once, and uses the years that load.
- Switched the app's version label to semantic versioning.

## 1.5.0 (October 8, 2026)
- Added: menu button (top left) that jumps to any section.
- Added: Travel dates with a popup calendar, shared with the family.
- Added: Weather with the forecast and 10-year typical weather for your dates.
- Changed: Who's traveling now sits below the miles and directions.
- Trip cost uses the number of nights from your travel dates.
- Needs updated Firebase rules (shared travel dates).

## 1.4.1 (October 8, 2026)
- Improved: family code entry (Show button, no auto-capitalization, forgives
  capitalization slips, clearer error message).
- Fixed: version label missing from the page.

## 1.4.0 (October 7, 2026)
- Added: Hidden gems section with local favorites for each city.
- Added: welcome popup and a How this works button.
- Changed: Who's traveling moved below the city buttons.
- Needs updated Firebase rules (hidden gem suggestions).

## 1.3.1 (October 7, 2026)
- Fixed: destination search now uses a built-in list of about 21,000 US
  towns, so it works even when online lookups are blocked.

## 1.3.0 (October 7, 2026)
- Added: Family additions section to review and remove everything the family
  added.
- Fixed: destination search accepts "Town ST" without a comma and full state
  names, offers family buttons inline, and falls back to a second lookup.

## 1.2.0 (October 7, 2026)
- Added: optional Google Maps link on suggestions, which also fills in the
  name from full-length links.
- Added: Copy suggestions for Claude button.
- Changed: the family code goes on one line in the Firebase rules.
- Needs updated Firebase rules (suggestion links).

## 1.1.0 (October 7, 2026)
- Added: suggest your own activities, restaurants and places to stay.
- Added: add your own destinations to the map.
- Needs updated Firebase rules (suggestions and destinations).

## 1.0.0 (October 7, 2026)
- First GitHub Pages release with the live family picks list on Firebase:
  halfway map for driving and flying, directions and flight searches, things
  to do, restaurants, places to stay, filters, trip cost and shared picks.
