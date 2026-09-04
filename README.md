# My Personal Dietitian

A private, local-first nutrition and fitness planning tool for a flexible Indian vegetarian fat-loss plan. It runs entirely in the browser and stores data in that browser's local storage; no backend, accounts, or external nutrition service are required.

## Run it

For full install/offline support, host this folder over HTTPS (or run it on `localhost` during development). Then open it in a mobile browser and choose **Install app** when the browser offers it. On iPhone/iPad, use Safari’s Share menu and choose **Add to Home Screen**. Opening `index.html` directly still works for normal local use, but browsers do not allow service workers or PWA installation from a `file://` URL.

## Project structure

- `index.html` — application shell and navigation
- `styles.css` — responsive visual system
- `app.js` — state management, adaptive planning logic, Ask My Dietitian responses, forms, logs, progress, and weekly review
- `manifest.webmanifest` — install metadata and standalone app settings
- `sw.js` — offline app-shell cache
- `icons/` — install/home-screen icons

## Personalization included

The planner responds to workout type and timing, rest days, hunger, energy, sleep, social dinners, egg preference, and today’s logged calories/protein. “Ask My Dietitian” supports practical requests such as a restaurant dinner, paneer sandwiches already eaten, a sweet craving, a missed workout, high hunger, pre-leg-day food, and limited ingredients. It suggests the remaining day instead of resetting the plan.

Daily targets remain editable planning estimates. The weekly review intentionally does not recommend automatic calorie cuts from a short-term weight fluctuation; use multiple weeks of trend, recovery, hunger, training performance, and adherence before considering a change.

## Data and future sync

All existing data continues to use `my-personal-dietitian-v1` in browser local storage—nothing is cleared or migrated away. `app.js` now writes through a small storage adapter with version and timestamp metadata, plus an export-shaped sync payload. A future cloud-sync provider can use this boundary to merge or back up data between phone and computer without rewriting the planning screens.

## Safety note

Targets are editable planning estimates, not medical advice. The app intentionally surfaces a prompt to seek a qualified clinician or dietitian for pregnancy/breastfeeding, medications, medical conditions, disordered eating, or requests for unsafe rapid loss.
