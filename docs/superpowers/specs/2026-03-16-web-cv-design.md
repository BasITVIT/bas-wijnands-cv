# Web-CV Design Spec — Bas Wijnands
**Datum:** 2026-03-16
**Status:** Goedgekeurd door gebruiker

---

## Doel

Een opvallende, interactieve web-CV pagina die bij het openen direct een "WOW"-effect geeft. Wordt samen met de print-CV (`cv.html`) meegestuurd naar recruiters. Zelfde kleurpalet, meer interactie en animaties.

---

## Bestand

`web-cv.html` — enkelvoudig HTML-bestand met embedded CSS + JavaScript

---

## Kleurpalet

- Achtergrond: `#0A1628` (dieper navy dan print-CV)
- Primair accent: `#00C2CB` (cyaan, met glow)
- Secundair accent: `#FF6B35` (oranje)
- Tekst: `#FFFFFF`
- Subtekst: `rgba(255,255,255,0.65)`
- Font: Inter (Google Fonts 400/600/700/800)

---

## Secties

### 1. Hero (fullscreen, direct WOW)

- Canvas-element (`<canvas>`) met geanimeerd netwerktopologie-effect:
  - ~60 nodes (cirkels) die langzaam bewegen
  - Verbindingslijnen tussen nodes die binnen 120px afstand zijn
  - Cyaan kleur met lage opacity (0.4–0.6)
- Bovenop canvas (centered):
  - Kleine label: `SYSTEM & NETWORK ENGINEER` (uppercase, letter-spacing, cyaan)
  - Naam met typewriter-animatie: `Bas Wijnands` (3.5–4rem, bold, wit)
  - Profieltekst fade-in na typewriter klaar
  - CTA-knop: `Bekijk mijn ervaring ↓` (cyaan border, hover-fill)
  - Scroll-indicator: pulserende pijl onderaan

### 2. Navigatie

- Verborgen bij start
- Verschijnt (slide-down) na scrollen voorbij hero
- Dark semi-transparant (`rgba(10,22,40,0.95)`) met backdrop-filter blur
- Links: Over mij · Ervaring · Skills · Opleiding
- Rechts: LinkedIn-icoon + e-mailadres

### 3. Over mij

- Foto links (cirkel, cyaan border, 160px) + tekst rechts
- Grote quote-mark decoratie in cyaan (opacity 0.1) achter tekst
- Profieltekst: zelfde content als print-CV (humanized versie)
- Stats-rij: `10+ jaar` · `6 werkgevers` · `2500 locaties` · `CCNA` — elk in een mini-card met cyaan top-border

### 4. Werkervaring

- Verticale tijdlijn: oranje lijn (3px) links
- Per job: oranje dot op lijn, kaart rechts
- Kaart: donker (`#0F1B2D`), cyaan bedrijfsnaam, oranje periode-badge
- Kaarten schuiven in vanuit rechts bij scrollen (Intersection Observer)
- Huidige baan (KPN) heeft cyaan glow op de kaart

### 5. Skills

- Sectietitel + twee kolommen:
  - Links: tech-tags als glowing chips (cyaan border + subtle glow)
  - Rechts: taalbalken geanimeerd (breedte groeit van 0 naar eindbreedte bij scrollen)
- Soft skills als oranje pill-badges

### 6. Opleiding & Certificeringen

- Grid van kaarten: 2 kolommen
- Cert-kaarten: icoon (🎓/🏆), naam, instituut, jaar
- CCNA-kaart heeft cyaan highlight (meest recente cert)

### 7. Footer / Contact

- Donkere strip
- Naam groot, links klikbaar (mail, LinkedIn)
- "Stuur me een bericht" CTA

---

## Animaties & Interactie

| Element | Animatie |
|---------|----------|
| Hero canvas | Continuous loop, requestAnimationFrame |
| Naam | Typewriter, 80ms per karakter, cursor blinkt |
| Profieltekst | Fade-in na 2s |
| Scroll-pijl | Pulserende bounce |
| Navigatie | Slide-down bij scroll > 100px |
| Werk-kaarten | IntersectionObserver, slide-in rechts |
| Taalbalken | IntersectionObserver, breedte-animatie |
| Stats | Count-up animatie (0 → getal) |
| CTA-knop hover | Background fill, scale 1.02 |

---

## Technisch

- Enkelvoudig HTML-bestand, embedded CSS + JS
- Geen externe libraries — vanilla JS
- Google Fonts: Inter
- Canvas API voor netwerk-animatie
- IntersectionObserver voor scroll-animaties
- `foto.jpg` naast het bestand (zelfde als print-CV)

---

## Inhoud (zelfde als print-CV, humanized)

Alle content identiek aan `cv.html` — zelfde bullets, zelfde profieltekst, zelfde skills, CCNA feb 2026.
