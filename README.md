# TRAPPRIJS

Concept-/democlone voor het **versneld ruimen van oude voorraad** via een
**trapsgewijze afprijzing** (stepped markdown) — een bewust andere methodiek
én een ander design dan de Firesale-demo.

## Het idee

- Restpartijen en incourante maten zakken in **vaste tredes**: bijv.
  nu **-30%**, na een paar dagen **-50%**, daarna **-70%**, en dan **weg**.
- **Wachten loont, maar op = op.** Dat creëert urgentie zonder een per
  seconde tikkende klok.
- De klant **rekent direct af** tegen de prijs van vandaag → geen
  betalen-achteraf-risico.
- Elke aankoop is een **losse, definitieve regel** → bestand tegen retour
  zonder herrekenlogica.
- Geen "van/voor"-spel: het is een eerlijke, voorspelbare markdown.

## Lokaal bekijken

Het is een statische site zonder build-stap. Open simpelweg `index.html`
in je browser. De tijd is voor de demo versneld; pas via **⚙ Demo-instellingen**
de tredelengte en kortingspercentages aan.

## Online zetten (GitHub + Vercel)

Deze repo bevat alleen een statische `index.html`, dus Vercel werkt zero-config.

1. Maak een lege repo aan op GitHub (bijv. `trapprijs`), zonder README.
2. Koppel en push lokaal:
   ```
   git remote add origin https://github.com/<jouw-account>/trapprijs.git
   git push -u origin main
   ```
3. Ga naar https://vercel.com → **Add New… → Project** → importeer de repo.
4. Framework Preset: **Other** (geen build command, output = root).
   Klik **Deploy**. Elke push naar `main` deployt voortaan automatisch.

## Status

Demo/concept — geen echte verkoop, productdata is fictief.
