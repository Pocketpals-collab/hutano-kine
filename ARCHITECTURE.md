# Architecture

## Current stack

Hutano.kine is a single-page, mobile-first static website built with native HTML, CSS and browser JavaScript.

- `index.html` contains page structure, metadata, French copy and all external booking links.
- `styles.css` contains the visual system, responsive layouts, focus states and reduced-motion support.
- `script.js` handles the mobile navigation, header state, progressive reveal effects and current footer year.
- `assets/` contains locally served responsive JPEG/WebP image variants.
- `favicon.svg` is the browser icon.

There is no package manager, framework, build pipeline, database, application server, form handler, cookie banner, analytics service or required telemetry.

## Runtime behaviour

A static host serves the files directly. The website does not collect or store patient information. All appointment buttons leave the website and open the practitioner's external Doctena profile.

**Booking, appointment availability, booking data, consent and any patient interaction are handled externally by Doctena.** Doctena is not bundled with this source and is outside this site's technical boundary.

## Site sections

The navigation targets sections inside `index.html`: approach, sports rehabilitation, services, about, FAQ and contact. No internal routing or server rewrite rules are required.

## External dependencies

- Doctena profile links for booking.
- No externally hosted fonts, scripts or stylesheets.
- Pexels photographs are stored locally; sources and licence notes are in `THIRD_PARTY_ASSETS.md`.
