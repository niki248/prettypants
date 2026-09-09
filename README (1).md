# Pretty Pants – feedback-side

En lille statisk side til at samle svar fra en gruppe kunder om Pretty Pants,
inkl. billedupload. Bygget til Netlify — ingen server, ingen database.

## Sådan lægger du den op

1. Opret et nyt repo på GitHub og upload alle filerne i denne mappe
   (`index.html`, `netlify.toml`).
2. Gå til [app.netlify.com](https://app.netlify.com) → **Add new site** →
   **Import an existing project** → vælg dit GitHub-repo.
3. Byggeindstillinger kan stå tomme (ingen build-kommando er nødvendig) —
   Netlify finder `netlify.toml` og udgiver roden af repoet.
4. Klik **Deploy**. Efter et minuts tid har du en live URL, du kan sende ud.

Netlify opdager automatisk formularen i `index.html`, fordi den har
`data-netlify="true"`. Du skal ikke gøre noget ekstra for at aktivere den.

## Sådan henter du svarene

1. Gå til dit site i Netlify → fanen **Forms**.
2. Der ligger en formular, der hedder `pretty-pants-feedback`, med alle
   indsendelser.
3. Klik ind på en indsendelse for at se svar og evt. uploadet billede
   (billedet vises som et link, du kan downloade).
4. Du kan eksportere alle svar som CSV via **Export to CSV** øverst på
   siden.

Tip: Under **Site settings → Forms → Form notifications** kan du sætte en
mail-notifikation op, så du får besked, hver gang der kommer et nyt svar.

## Skift billeder i toppen

De fire farvede felter øverst på siden er pladsholdere. Læg dine egne
billeder i en mappe kaldet `images/` (allerede oprettet) og ret hver
`.swatch`-blok i `index.html` til at indeholde:

```html
<div class="swatch"><img src="images/pretty-pants-1.jpg" alt=""></div>
```

## Begrænsninger at kende til

- Netlify's gratis plan tillader 100 formular-indsendelser om måneden —
  rigeligt til en lille gruppe, men værd at holde øje med hvis I bruger den
  til flere ting.
- Maks. filstørrelse pr. upload er ca. 8 MB på gratis planen.
- Feltet "Må vi bruge det som citat?" og "Må vi se dem på?" er ikke
  obligatoriske — kun mailadressen er det. Ret `required` i `index.html`,
  hvis du vil ændre det.
