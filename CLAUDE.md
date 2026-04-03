# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Profil développeur

- **Nom** : Patrick Mekongo
- **Formation** : BTS SIO SISR 1ère année, Paris (Ingetis)
- **Objectifs** : décrocher un stage IT + commercialiser des projets SaaS/mobile
- **Préférences** : explications step-by-step, prompts courts, `/compact` régulier

## Environnement local

- OS : Windows 11
- Terminal : Git Bash
- Node.js : v24
- Claude Code : v2.1.90
- Éditeur : VS Code
- PHP/MySQL local : AMPPS (`htdocs/`)

## Projets actifs

### 1. Portfolio (ce repo)
Single-page HTML/CSS/JS publié sur GitHub Pages.
- **URL live** : https://patrickmekongo19-droid.github.io/portfolio/
- **Fichier unique** : `index.html` (~1750 lignes, tout inline)
- **Deploy** : `git push origin main` → GitHub Pages auto (1-2 min)

### 2. cv-generator (sous-dossier)
Application PHP + MySQL locale (AMPPS). Voir section Architecture ci-dessous.

### 3. Futur SaaS — Générateur de CV (en cours de conception)
- Stack cible : **Supabase** (BDD/auth) · **Vercel** (déploiement) · **Stripe** (paiement) · **Clerk** (authentification) · **Cloudflare** (CDN/DNS) · **Namecheap** (domaine)
- Monitoring : **PostHog** (analytics) · **Sentry** (erreurs) · **Upstash** (cache Redis) · **Pinecone** (vectoriel/IA)

### 4. App mobile — Drop (en conception)
Événements et bons plans Paris. Stack non finalisée.

## Architecture portfolio (index.html)

**Sections HTML dans l'ordre** :
| ID | N° | Contenu |
|---|---|---|
| `#hero` | — | Nom, titre, badge disponibilité |
| `#pratique` | 01 | Ce que je sais faire (4 blocs `.p-meta`) |
| `#competences` | 02 | Stack technique (4 groupes) |
| `#parcours` | 03 | Timeline : BTS SIO SISR Ingetis, CNIL, Bac L… |
| `#experiences` | 04 | Mission IT professionnelle |
| `#projets` | 05 | 5 projets avec screenshots lightbox |
| `#autres-exp` | 06 | Smitom-Lombric, Picnic CDI, Atelier filmique |
| `#cherche` | 07 | Stage 29 juin – 30 juillet 2026 |
| `#supervision` | 08 | PRTG, Nagios, Centreon, Zabbix + schéma SVG |
| `#cv-dl` | 09 | Téléchargement `assets/cv-patrick-mekongo.pdf` |
| `#about` | 10 | À propos |
| `#contact` | 11 | Formulaire mailto + LinkedIn/GitHub/email |

**JS inline (fin de fichier)** : curseur custom, nav scroll, back-to-top, parallax, scroll reveal (`.reveal`→`.visible`), lightbox, copy email, formulaire contact, **Inspi chatbot SVG animé** (IIFE séparé juste avant `</body>`).

**Conventions** : Barlow Condensed (titres) / Barlow (corps) / DM Mono (labels). Palette : `#0a0a0a` noir · `#c8a96d` or · `#4f7ef7` bleu · `#34d399` vert. Esthétique luxe éditoriale — pas d'emojis.

## Architecture cv-generator (PHP/MySQL)

Flux : `index.html` → POST → `save.php` → BDD → redirect `cv.php?id=`

- **Base** : `générateur_cv`, table `candidats`
- **Identifiants** : `root` / `mysql`
- **Accès local** : `http://localhost/cv-generator/`

## Assets portfolio

```
assets/
├── cv-patrick-mekongo.pdf
├── img/   # screenshots projets + inspi.jpg (avatar chatbot)
└── video/ # démo générateur de CV
```

## Contact

- Email : patrickmekongo19@gmail.com
- LinkedIn : https://www.linkedin.com/in/patrick-koa-mekongo-767476353
- GitHub : https://github.com/patrickmekongo19-droid
