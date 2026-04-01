# LAWYALTY

Rechtsorientierung. Kein Anwalt, aber an deiner Seite.

## Repo-Struktur

```
lawyalty/
├── index.html              ← Landing Page (Wizard + Freemium/Premium)
├── favicon.svg             ← Logo-Icon
├── danke/index.html        ← Stripe Success-Redirect
├── impressum/index.html    ← Placeholder
├── datenschutz/index.html  ← Placeholder
├── agb/index.html          ← Placeholder
├── abgrenzung/index.html   ← Placeholder (RDG-Abgrenzung)
├── robots.txt
├── netlify.toml            ← Headers, Caching, Security
└── _redirects              ← Clean URLs
```

## Setup

### 1. GitHub Repo erstellen
```bash
git init
git add .
git commit -m "LAWYALTY v1 — Landing Page + Wizard + Danke"
git remote add origin git@github.com:DEIN-USERNAME/lawyalty.git
git push -u origin main
```

### 2. Netlify verbinden
- Netlify Dashboard → New Site → Import from Git → GitHub → lawyalty
- Build command: (leer lassen)
- Publish directory: `.`
- Deploy

### 3. Domain verbinden
- Netlify → Domain Settings → Add custom domain → `lawyalty.de`
- GoDaddy DNS: CNAME `www` → `[dein-site-name].netlify.app`
- Oder Netlify DNS nutzen (Nameserver bei GoDaddy umstellen)

### 4. Stripe Payment Link
- Stripe Dashboard → Payment Links → Neu
- Produkt: "LAWYALTY Premium-Report" → 19,00 €
- After payment → Redirect: `https://lawyalty.de/danke`
- Link kopieren → im Wizard-Code den `showToast('Weiterleitung …')` durch `window.location.href = 'DEIN_STRIPE_LINK'` ersetzen

### 5. Brevo Integration
- Brevo API-Key bereitstellen
- Wizard Step 4 (E-Mail) an Brevo API anbinden
- Tags: topic + free/premium

## Stack

- Pure HTML/CSS/JS (kein Build-Step)
- Netlify (Hosting)
- Stripe (Payment)
- Brevo (E-Mail)
- Claude API (Premium-Report Generation — Phase 2)

## HIGHERPlan GmbH
