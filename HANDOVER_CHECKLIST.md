# Independent launch checklist

## Ownership and access

- [ ] Hosting account is opened in the practice owner's name.
- [ ] Domain registrar and DNS access are controlled by the practice owner.
- [ ] A competent technical contact has the minimum access needed for launch.
- [ ] Multi-factor authentication and account recovery details are enabled and documented.
- [ ] This package is committed to a private repository owned by the practice.

## Content and legal approval

- [ ] Practitioner name, title, address and contact details are confirmed.
- [ ] Final service list and sports-rehabilitation scope are approved.
- [ ] All medical wording is reviewed for accuracy and local professional requirements.
- [ ] Legal notice is approved and published at `legal/legal-notice.html`.
- [ ] Privacy information is approved and published at `legal/privacy.html`.
- [ ] Footer placeholders are replaced by working links to those pages.
- [ ] Doctena profile URL and every booking button are tested.
- [ ] Image sources/licences remain recorded in `THIRD_PARTY_ASSETS.md`.

## Hosting and domain

- [ ] Package contents are uploaded with `index.html` at the web root.
- [ ] Apex and `www` DNS records use the exact targets supplied by the new host.
- [ ] Conflicting DNS records are removed without disturbing email or other services.
- [ ] One canonical domain is selected and the alternative redirects to it.
- [ ] HTTPS certificate is valid for every public host name.
- [ ] HTTP redirects to HTTPS.
- [ ] A custom 404 response or host default is reviewed.

## Quality assurance

- [ ] Test current versions of Chrome, Safari, Firefox and Edge where available.
- [ ] Test representative phone, tablet and desktop widths.
- [ ] Complete keyboard-only navigation and visible-focus checks.
- [ ] Confirm reduced-motion preference is respected.
- [ ] Check heading order, landmarks, image alternative text and colour contrast.
- [ ] Run an automated accessibility check and manually review its findings.
- [ ] Run a performance audit; confirm images are compressed and no broken requests occur.
- [ ] Check every internal anchor, footer item and external Doctena link.
- [ ] Confirm the site has no unexpected cookies, analytics or network calls.

## Backups and operation

- [ ] Hosting backups or versioned deployments are enabled.
- [ ] The private repository is the source of truth for future changes.
- [ ] A clean checkout has been previewed and published to a non-production test address.
- [ ] Restore procedure is documented and tested.
- [ ] Domain, certificate and hosting renewal contacts are recorded.
- [ ] A named person is responsible for future content, legal and image-licence updates.
- [ ] The live Hutano.kine site is switched only after the independent host passes all checks.
