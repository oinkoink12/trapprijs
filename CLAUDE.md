# TRAPPRIJS / iBOOD Aftrap

> **Push nooit automatisch naar GitHub — wacht altijd op een expliciete opdracht van de gebruiker.**

## Wat is dit

`iBOOD Aftrap` (repo-/concepnaam: TRAPPRIJS) — een concept-/demo voor het
**versneld ruimen van oude voorraad** via een **trapsgewijze afprijzing**
(stepped markdown). Restpartijen zakken in **vaste tredes** (bijv. -30% →
-50% → -70% → weg). Wachten loont, maar **op = op**: urgentie zonder een
per seconde tikkende klok. De klant rekent direct af tegen de prijs van
vandaag; elke aankoop is een losse, definitieve regel.

Dit is bewust een **andere methodiek én ander design** dan de zusterrepo
[`firesale`](../firesale), die een doorlopende, tijdgedreven prijserosie
gebruikt. Twee UX-experimenten voor hetzelfde iBOOD-opruimprobleem, op
dezelfde echte productdataset.

## Structuur

Statische site, **geen build-stap**. Alles zit in één bestand:

- `index.html` — HTML + CSS + JS in één file.
  - **Productdata**: `const PRODUCTS = [ … ]` staat als **één enkele regel
    van ~49 KB** (rond regel 163), gedeeld met de `firesale`-dataset.
    Velden o.a. `brand, title, shortTitle, price, salePrice, imageUrl,
    category`; daarna genormaliseerd naar `cat`, `name`, en een random
    `stock`.
  - **Kernlogica (JS)**: `buildSteps(n, first, last)` (bouwt de
    kortingstrap, lineair verdeeld, strikt oplopend), `renderLegend`,
    `render` (deals + dynamisch geschaalde tread-balkjes), `nextStepText`,
    `priceAt`, `tick` (zet elke `dayLen` sec. een trede lager), `buy`,
    demo-instellingen (`openSettings`/`applySettings`).
  - **Demo-instellingen**: tredelengte (sec.), **aantal treden (2–12)**,
    en eerste/laatste kortingspercentage. Aantal treden bepaalt hoeveel
    stappen de afprijstrap krijgt.
- `README.md` — bevat het uitgebreide concept + deploy-instructies.

## Werkwijze-aandachtspunten

- De enorme `PRODUCTS`-regel maakt `index.html` te groot voor de Read/Edit-
  tools in één keer. Gebruik regelgerichte bewerkingen (`sed -i` met
  regelnummers, of de `r`+`d`-truc) i.p.v. de Edit-tool op die regel.
- `node` is lokaal beschikbaar (portable install in
  `C:\Users\<user>\node-v24.15.0-win-x64`, in user-PATH). Handig om de
  inline JS te valideren met `vm.Script` en `buildSteps` te testen vóór
  commit.
- Lokaal bekijken: open `index.html` direct in de browser. Online via
  Vercel (zero-config, output = root).

## Status

Demo/concept — geen echte verkoop. Productdata is reëel iBOOD-materiaal
maar de prijslogica is fictief/versneld voor demodoeleinden.
