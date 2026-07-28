# Hutano.kine independent hosting handover

This package contains the standalone source for the current Hutano.kine website only. It does not contain the Hutano marketplace, PocketPals, booking-system code, patient data, server code or vendor-specific deployment files.

The exported website content and privacy/legal placeholders match the live Hutano.kine source snapshot dated 28 July 2026. Preparing this package did not change or unpublish the live site.

## What this site needs

Hutano.kine is a plain static website. It needs only a standard web host that can serve HTML, CSS, JavaScript, SVG, JPEG and WebP files over HTTPS.

There is:

- no build step;
- no database or server-side application;
- no login or form submission;
- no analytics or telemetry requirement;
- no API key, environment variable or vendor secret;
- no dependency installation.

The owner supplies and controls the hosting account, domain registrar account and DNS account.

## Files at a glance

- `index.html` — all public page structure and French website copy
- `styles.css` — colours, typography, layout and responsive behaviour
- `script.js` — mobile menu, header state, reveal effects and footer year
- `favicon.svg` — browser icon
- `assets/` — local responsive JPEG and WebP photographs
- `legal/README.md` — the agreed location and instructions for future legal/privacy pages
- `ARCHITECTURE.md` — current stack and structure
- `THIRD_PARTY_ASSETS.md` — Pexels source and licence notes
- `OWNERSHIP_AND_HANDOVER.md` — ownership boundaries and account responsibilities
- `HANDOVER_CHECKLIST.md` — launch checklist
- `VERIFICATION.md` — checks run on this export
- `FILE_MANIFEST_SHA256.txt` — integrity checksums for package files

## Preview locally

From the package directory, run:

```bash
python3 -m http.server 8080
```

Then open:

```text
http://localhost:8080/
```

Stop the preview with `Ctrl+C`.

Opening `index.html` directly may work, but a local web server gives a more accurate preview.

## Publish on standard static hosting

No compilation is required.

### File-upload hosting

1. Open the host's public web-root directory, often named `public_html`, `www`, `htdocs` or `site`.
2. Upload the contents of this package, preserving the `assets/` and `legal/` directories.
3. Ensure `index.html` sits directly in the web root, rather than inside an extra nested directory.
4. Set `index.html` as the default document if the host does not detect it automatically.
5. Enable HTTPS and an automatic HTTP-to-HTTPS redirect.

### Git-based static hosting

Use the package root as the repository root. Configure:

- build command: none or blank;
- publish/output directory: `.` (the repository root);
- runtime/framework preset: static HTML or none;
- environment variables: none.

Do not publish `.git/`, local editor settings or operating-system files.

## Point the domain

First add the final domain inside the new host so the host knows which website should answer for it. The host will then provide one of these destinations:

- one or more IPv4/IPv6 addresses; or
- a host name used as a CNAME target.

Set DNS as follows, using the exact values supplied by the chosen host:

1. **Apex/root domain** (`example.com`):
   - use `A` records for supplied IPv4 addresses and `AAAA` records for supplied IPv6 addresses; or
   - use `ALIAS`, `ANAME` or CNAME-flattening if the host supplies only a host-name target and the DNS provider supports it.
2. **`www` host** (`www.example.com`):
   - use a `CNAME` to the host-name target; or
   - point it to the apex according to the host's instructions.
3. Remove conflicting `A`, `AAAA` or `CNAME` records for the same host names.
4. Do not replace the domain's nameservers unless the new hosting/DNS provider explicitly requires full DNS control and all existing mail/service records have been copied first.
5. Choose one canonical address (`example.com` or `www.example.com`) and redirect the other to it.
6. Wait for DNS validation, issue the TLS certificate, then confirm both HTTP and HTTPS requests end at the canonical HTTPS address without certificate warnings.

DNS values cannot be filled in before a host is chosen because the new host owns the required target values.

## Update public content

All visible wording is in `index.html`.

- Edit text between HTML tags without removing the surrounding tags.
- Keep the page language as French unless the full content is intentionally translated.
- Preserve heading order, link labels and image alternative text for accessibility.
- Review the complete final service list with the practice before publishing changes.

After editing, preview locally and test at mobile and desktop widths before uploading the changed files.

## Update images

The site uses local responsive image sets in `assets/`.

For a simple like-for-like replacement:

1. Prepare the new image in the same aspect ratio as the image being replaced.
2. Export the sizes and formats named in `index.html`.
3. Replace the matching files in `assets/` without changing their file names; or update every matching path in `index.html`.
4. Update the image `alt` text in `index.html` so it describes the new image accurately.
5. Optimise the files before publishing and record the new source/licence in `THIRD_PARTY_ASSETS.md`.

Current image groups:

- `renforcement-guide-*` — main hero image
- `entrainement-adapte-*` — sports-rehabilitation section
- `taping-recuperation-*` — about section portrait image
- `mobilite-reformer-*` — about section secondary image

## Update the Doctena booking link

Booking is external. The current Doctena URL appears eight times in `index.html`:

```text
https://www.doctena.lu/fr/specialite/kinesitherapeute/tinashe-nicole-2150760#26299
```

When the booking destination changes, replace every occurrence in `index.html`, then test every “Prendre rendez-vous”, “Ouvrir Doctena” and availability link. Keep external links opening safely with `target="_blank"` and `rel="noopener noreferrer"`.

## Add legal notice and privacy information

The current footer deliberately shows “Informations légales à finaliser” and “Confidentialité à finaliser”. Final text must be supplied or approved by the practice's qualified legal/privacy adviser before independent launch.

Future pages belong at:

- `legal/legal-notice.html`
- `legal/privacy.html`

Instructions are in `legal/README.md`. Once approved pages exist, replace the two footer placeholder `<span>` elements in `index.html` with links to those files. Legal and privacy content is website content owned and maintained by the practice.

## Version control and backups

This export is ready to place in a private Git repository. A `.gitignore` is included. Before launch:

1. create a private repository owned by the practice;
2. commit this exact handover as the baseline;
3. protect the main branch and require reviewed changes where practical;
4. keep the repository separate from hosting-provider access;
5. enable host backups or retain versioned deployment archives;
6. test restoration from a clean checkout at least once.

See `HANDOVER_CHECKLIST.md` for the complete launch sequence.
