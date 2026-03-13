# CLAUDE.md — Dutch Legal AI Benchmark

## Taal & Communicatie
- Communiceer in het **Nederlands**, tenzij anders gevraagd
- Code en technische documentatie in het **Engels**
- Wees direct en bondig — geen overbodige uitleg tenzij gevraagd

---

## Projectoverzicht

**Dutch Legal AI Benchmark 2026** is een proof-of-concept evaluatietool die juridische AI-oplossingen vergelijkt op de Nederlandse markt. Statische PWA met interactief dashboard.

### Wat het doet
- Benchmarkt 5 juridische AI tools (GenIA-L, Harvey, Claude 3.7, GPT-4o, Luminance) tegen 12 juridische prompts
- Evalueert op 5 dimensies: juridische correctheid, volledigheid, bronvermelding, redeneerkwaliteit, hallucinaties
- Panel van 4 juridische experts geeft blind reviews
- Dashboard met ranking tabellen, radar profielen, prompt library en methodologie

### Tech Stack

| Technologie | Doel |
|---|---|
| HTML/CSS/JS | Vanilla stack, geen build tools |
| Chart.js | Visualisaties (bar, radar, category charts) |
| Service Worker | PWA offline support |
| Cormorant Garamond + DM Sans | Typography |

### Bestandsstructuur

```
Legal/
├── Dutch_Legal_AI_Benchmark_PoC.docx  → Project specificatie
└── files/
    ├── index.html       → Hoofd-app (alle data & styles inline)
    ├── manifest.json    → PWA configuratie
    ├── sw.js            → Service Worker voor caching
    └── icon-*.svg       → PWA iconen
```

---

## Workflow

### Plan First
- Enter plan mode voor **elke niet-triviale taak** (3+ stappen of architectuurbeslissingen)
- Schrijf het plan naar `tasks/todo.md` met checkbare items
- Wacht op bevestiging voordat je begint met implementatie
- Als iets misgaat → **stop, re-plan, en communiceer waarom**

### Verificatie
- Markeer een taak **nooit** als afgerond zonder bewijs dat het werkt
- Test in browser, check console op errors
- Stel jezelf de vraag: *"Would a staff engineer approve this?"*

---

## Code Kwaliteit

### Principes
- **Simplicity first** — maak elke wijziging zo simpel mogelijk
- **Root cause** — geen tijdelijke fixes, zoek de oorzaak
- **Minimal impact** — raak alleen aan wat nodig is

### Stijl
- Vanilla JS, geen frameworks, geen build step
- Data is hardcoded in index.html (simulatiedata)
- Volg bestaande patronen (Chart.js config, DOM structuur)

---

## Bug Fixing

### Aanpak
- Bij een bugreport → analyseer en fix autonoom
- Reproduceer het probleem eerst, fix daarna
- Als de fix niet evident is: beschrijf je hypothese voordat je implementeert

### Debugging
- Primary stack: vanilla JavaScript, CSS/HTML
- Bij data-issues: check **data types eerst** voordat je logica-fouten aanneemt
- Check Chart.js configuratie bij visualisatieproblemen

---

## UI Development
- Verifieer elke UI-wijziging visueel voordat je verder gaat
- Bevestig **welke specifieke elementen** de gebruiker bedoelt voordat je gaat editen
- Na elke wijziging: check dat styles daadwerkelijk toegepast worden
- Test light/dark theme toggle na wijzigingen
- Controleer mobile responsiveness

---

## Zelfverbetering

### Lessons Learned
- Na **elke correctie** van de gebruiker → update `tasks/lessons.md`
- Schrijf regels die dezelfde fout voorkomen
- Review lessons aan het begin van een sessie

---

## Wat NIET te doen
- Geen bestanden aanraken die buiten scope vallen
- Geen ongevraagde refactors
- Geen build tools of npm introduceren — dit is een zero-dependency project
- Niet stilletjes errors negeren
- Geen `console.log` debugging achterlaten in production code
