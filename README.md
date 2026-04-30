# Bryllupsinvitation · Sascha &amp; Klodian

Digital bryllupsinvitation til **Sascha &amp; Klodian** den 10. oktober 2026 i Tirana, Albanien.

En enkeltsides hjemmeside med:

- Åbningsanimation med skovgrønne fløjlsgardiner
- Sort/hvidt parfoto i hero
- Poetisk invitationstekst
- Save the date med dato og venue
- Live countdown ned til dagen
- Tidsplan for bryllupsdagen med håndtegnede ikoner
- RSVP-sektion
- Komplet gæsteguide (rejse, ophold, dresscode, vejr, sted)
- Cremefarvet og dyb skovgrøn æstetik

Bygget i ren HTML, CSS og JavaScript — ingen frameworks, ingen byggetrin, ingen afhængigheder.

---

## Sådan ser du den lokalt

Dobbeltklik på `index.html`, eller åbn den fra terminalen:

```bash
open index.html       # macOS
xdg-open index.html   # Linux
start index.html      # Windows
```

For en lokal webserver (anbefalet, så fonte og billeder loader korrekt):

```bash
cd Weddinginvitation
python3 -m http.server 8000
# Åbn så http://localhost:8000 i din browser
```

---

## Filstruktur

```
Weddinginvitation/
├── index.html              # Hele invitationen i én fil
├── images/
│   ├── couple.jpg          # Sort/hvidt parfoto (hero)
│   ├── glasshouse.jpg      # Glashuset på Kazerma
│   └── brickbuilding.jpg   # Murstenshuset med vinranker
├── README.md
└── .gitignore
```

---

## Tilpasning

Al tekst og indhold ligger i `index.html`. Søg efter sektionerne med kommentarer som `<!-- HERO -->`, `<!-- TIMELINE -->`, osv.

### Almindelige ændringer

| Hvad du vil ændre | Hvor i `index.html` |
| --- | --- |
| Navne (Sascha, Klodian) | Søg på `Sascha` og erstat alle steder |
| Datoen 10.10.2026 | Søg på `10.10.2026` og `10·10·2026` |
| Countdown-måldatoen | Linjen `const target = new Date('2026-10-10T17:00:00+02:00')` |
| RSVP-deadline | Søg på `10. juli 2026` |
| Kontakt-e-mail | Søg på `Saschacocodaniels` |
| Tidsplan på bryllupsdagen | Sektionen `<!-- TIMELINE / THE DAY -->` |
| Farver (cream, grøn) | CSS-variablerne i `:root { … }` øverst i `<style>` |

### Skift et billede

Erstat filerne i `images/` med dine egne (samme filnavne — eller opdater stien i `index.html`). Anbefalede dimensioner: 1200 × 1600 px, JPEG, ~75 % kvalitet.

### Skift fontene

Fontene loades fra Google Fonts øverst i `<head>`. De nuværende:

- **Playfair Display** — display og overskrifter
- **Cormorant Garamond** — brødtekst og kursiv
- **Pinyon Script** og **Allura** — håndskrevne accenter

Skift link-tagget hvis du vil bruge andre fonte.

---

## Deploy

### Mulighed 1 · GitHub Pages (gratis, anbefalet)

1. Push repoet til GitHub (se sektionen nedenfor)
2. Gå til repoets indstillinger → **Pages**
3. Vælg **Deploy from a branch** og pegg den på `main` / `(root)`
4. Inden for 1–2 minutter er siden live på `https://olivergjersoe.github.io/Weddinginvitation/`

### Mulighed 2 · Netlify Drop (hurtigste, ingen konto behøvet)

1. Gå til [app.netlify.com/drop](https://app.netlify.com/drop)
2. Træk hele `Weddinginvitation/`-mappen ind
3. Du får et delbart link med det samme

Med en gratis Netlify-konto kan du tilknytte et eget domæne (`saschaogklodian.dk` eller lignende).

### Mulighed 3 · Vercel

1. Login på [vercel.com](https://vercel.com) med GitHub
2. Importer repoet
3. Deploy uden ændringer (det er en statisk side)

### Eget domæne

Alle tre platforme understøtter custom domæner. Køb fx hos [simply.com](https://simply.com) eller [namecheap.com](https://www.namecheap.com), og pegg DNS'en mod hosting-platformen.

---

## Push til GitHub

Repoet er allerede initialiseret med ét commit. Pushing første gang:

```bash
cd Weddinginvitation
git remote add origin https://github.com/olivergjersoe/Weddinginvitation.git
git branch -M main
git push -u origin main
```

Senere ændringer:

```bash
git add .
git commit -m "Beskrivelse af ændringen"
git push
```

---

## Browserkompatibilitet

Testet og virker i:

- Safari 16+ (iOS &amp; macOS)
- Chrome 100+
- Firefox 100+
- Edge 100+

Bruger moderne CSS (`aspect-ratio`, CSS-variabler, `IntersectionObserver`). Ingen polyfills nødvendige for moderne enheder.

---

## Tilgængelighed

- Gardin-overlay kan åbnes med tastatur (Enter eller Space)
- `prefers-reduced-motion` er respekteret — animationer dæmpes for brugere der har den indstilling slået til
- Semantiske HTML5-elementer (`main`, `section`, `h1`–`h3`)
- `alt`-tekster på alle billeder

---

## Credits

- Fonte: [Google Fonts](https://fonts.google.com)
- Ikoner: Custom inline SVG (intet eksternt bibliotek)
- Bygget med hjælp fra Claude (Anthropic)
