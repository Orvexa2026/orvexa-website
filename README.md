# Orvexa — websitebestanden

## Inhoud
- `index.html`: de complete onepager
- `styles.css`: vormgeving en mobiele weergave
- `script.js`: mobiel menu en automatisch jaartal
- `favicon.svg`: browsericoon
- `CNAME`: koppeling met `orvexa.nl`
- `orvexa-banner.png`: de aangeleverde Orvexa-banner

## Controleer vóór publicatie
1. Controleer of `info@orvexa.nl` het juiste zakelijke e-mailadres is.
2. Controleer of de dienstbeschrijvingen overeenkomen met het aanbod van Orvexa.
3. Voeg indien nodig je juridische bedrijfsgegevens en privacyverklaring toe.

## Gratis publiceren met GitHub Pages
1. Ga naar https://github.com en maak gratis een account aan of log in.
2. Klik op `+` → **New repository**.
3. Kies de naam `orvexa-website`, selecteer **Public** en maak de repository aan.
4. Klik **Add file** → **Upload files** en upload alle bestanden uit deze map, inclusief `orvexa-banner.png`.
5. Klik **Commit changes**.
6. Open **Settings** → **Pages**.
7. Bij **Build and deployment** kies je **Deploy from a branch**, branch `main`, map `/ (root)`, en klik **Save**.
8. Nadat de repository is aangemaakt, open **Settings** → **Pages** en vul bij **Custom domain** `orvexa.nl` in. Klik **Save**. GitHub kan zelf een `CNAME`-bestand aanmaken.
9. Ga pas daarna naar TransIP om DNS in te stellen.

## Domein koppelen bij TransIP
1. Log in op https://www.transip.nl/cp/.
2. Ga naar **Domein** en klik op `orvexa.nl` (niet alleen het selectievakje aanvinken).
3. Zoek **DNS instellingen**. Als de TransIP-instellingen aanstaan, schakel ze uit om eigen records te kunnen beheren. Controleer eerst bestaande records.
4. Voeg voor de website de vier GitHub Pages A-records toe met naam `@`:
   - `185.199.108.153`
   - `185.199.109.153`
   - `185.199.110.153`
   - `185.199.111.153`
5. Voor `www` voeg je een CNAME-record toe: naam `www`, waarde `JOUWGITHUBNAAM.github.io.` (vervang dit door je eigen GitHub-gebruikersnaam of organisatie-hostnaam; niet de repositorynaam).
6. Verwijder geen MX-, SPF-, DKIM- of DMARC-records. Die kunnen nodig zijn voor zakelijke e-mail. Als er bestaande A/AAAA-records voor `@` zijn, controleer die voordat je ze vervangt. GitHub documenteert ook IPv6 AAAA-records; voeg die alleen toe als je de volledige set goed kunt instellen.
7. Ga terug naar GitHub **Settings → Pages**. Wacht tot de domeincontrole is geslaagd en vink **Enforce HTTPS** aan.
8. DNS-wijzigingen kunnen tot 24 uur nodig hebben. Test daarna `https://orvexa.nl` en `https://www.orvexa.nl`.

## Belangrijk
GitHub Pages is gratis voor een statische site in een public repository. De domeinregistratie bij TransIP blijft je bestaande domeinkost. Pas geen e-mailrecords aan zonder ze eerst te controleren.

Officiële hulp:
- GitHub Pages custom domain: https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site
- TransIP DNS beheren: https://www.transip.nl/knowledgebase/305-dns-nameservers-aanpassen-via-controlepaneel
