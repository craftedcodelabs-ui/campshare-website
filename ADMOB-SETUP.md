# CampShare – AdMob app-ads.txt (Play Store live)

Publisher-ID aus AdMob: **pub-7130450566926940**

## Schritt 1 – Datei (fertig)

Inhalt von `app-ads.txt`:

```
google.com, pub-7130450566926940, DIRECT, f08c47fec0942fa0
```

## Schritt 2 – Auf GitHub Pages veröffentlichen

### A) CampShare-Website (mit deployen)

Die Datei liegt bereits in diesem Repo:

- Pfad im Repo: `website/app-ads.txt`
- Nach Push auf `main` erreichbar unter:  
  `https://craftedcodelabs-ui.github.io/campshare-website/app-ads.txt`

```powershell
cd d:\AppCreate\CampShare\website
git add app-ads.txt ADMOB-SETUP.md github-io-root/
git commit -m "Add AdMob app-ads.txt for publisher verification"
git push origin main
```

### B) Stammdomain (für AdMob **Pflicht**)

AdMob crawlt die **Stammdomain** aus der Play Console (`craftedcodelabs-ui.github.io`), nicht den Unterordner.

→ Siehe **`github-io-root/README.md`**: Repository `craftedcodelabs-ui.github.io` mit derselben `app-ads.txt`.

**Ziel-URL für AdMob:**

https://craftedcodelabs-ui.github.io/app-ads.txt

## Schritt 3 – Play Console abgleichen

In der Play Console muss unter **Store-Eintrag → Kontakt → Website** stehen:

```
https://craftedcodelabs-ui.github.io/campshare-website/
```

(Domain-Host muss **craftedcodelabs-ui.github.io** sein – passt bereits.)

## Schritt 4 – In AdMob verifizieren

1. AdMob → **Apps** → CampShare → **App-Einstellungen** → **app-ads.txt**
2. **Crawling starten** / Verifizierung abwarten (oft 15–30 Min., manchmal länger)
3. Status sollte **„Verifiziert“** werden

## Checkliste vor Go-Live

- [ ] `app-ads.txt` auf `craftedcodelabs-ui.github.io/app-ads.txt` erreichbar
- [ ] Play Console Website = `https://craftedcodelabs-ui.github.io/campshare-website/`
- [ ] AdMob App mit Package `com.craftedcodelabs.campshare` verknüpft
- [ ] Release-Build mit echten AdMob-IDs (nicht Test-IDs)
- [ ] Play Console ↔ AdMob verknüpft (Monetarisierung)

## AdMob-IDs in der App (bereits eingetragen)

| Typ | ID |
|-----|-----|
| App-ID | `ca-app-pub-7130450566926940~9801287217` |
| Rewarded | `ca-app-pub-7130450566926940/6428862884` |
