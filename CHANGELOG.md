# BrewAberKirk Halfway Point App: changelog

Versions follow semantic versioning (MAJOR.MINOR.PATCH):

- **MAJOR** goes up for changes that need you to redo setup or that would
  lose saved data.
- **MINOR** goes up for new features. These sometimes need updated Firebase
  rules; the entry will say so.
- **PATCH** goes up for fixes and small adjustments.

The version number is shown at the bottom of the app.

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
