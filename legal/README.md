# Legal and privacy page location

The current website footer contains placeholders because the final legal notice and privacy information have not been supplied.

Place approved final pages here:

- `legal-notice.html` — publisher/practice identity, professional and contact details, hosting details and other locally required legal notice content.
- `privacy.html` — data-controller identity, data processed by this website, purpose/legal basis, retention, recipients, rights, contact/complaint information and any required cookie/analytics explanation.

Use the same language and visual style as the main French website. Once these files exist, replace the two placeholder `<span>` elements inside `.footer-legal` in `index.html` with links:

```html
<a href="legal/legal-notice.html">Informations légales</a>
<a href="legal/privacy.html">Confidentialité</a>
```

Do not copy generic legal text without qualified review for the practice's actual identity, jurisdiction, hosting setup, Doctena relationship and data practices.
