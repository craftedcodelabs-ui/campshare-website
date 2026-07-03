# CampShare Website

Statische Website für **Google Play** (Datenschutz, Konto löschen, Impressum, AGB).

## Live-URLs (GitHub Pages)

| Seite | URL |
|-------|-----|
| Start | https://craftedcodelabs-ui.github.io/campshare-website/ |
| Datenschutz | …/datenschutz.html |
| Konto löschen | …/konto-loeschen.html |
| AGB | …/nutzungsbedingungen.html |
| Impressum | …/impressum.html |
| Kontakt | …/kontakt.html |

Alle URLs auch in `play-store-urls.txt` zum Kopieren in die Play Console.

## Deploy

Automatisch bei Push auf `main` (GitHub Actions → Pages).

```powershell
cd d:\AppCreate\CampShare\website
git add .
git commit -m "Update legal pages for CampShare 1.0"
git push origin main
```

Erstes Setup: `..\scripts\setup_github_website.ps1`

## Vor Play-Store-Veröffentlichung

1. **Impressum:** Postadresse in `impressum.html` ergänzen
2. **E-Mails:** `@campshare.app` durch deine echte Domain ersetzen (oder Weiterleitung einrichten)
3. **Play Console:** URLs aus `play-store-urls.txt` eintragen
4. **App:** `lib/legal_urls.dart` zeigt bereits auf GitHub Pages


## Google Sites (Alternative)

Kein eigenes Hosting nötig – Inhalte in **Google Sites** einfügen:

👉 **[google-sites/ANLEITUNG.md](google-sites/ANLEITUNG.md)** – Schritt-für-Schritt-Anleitung  
📄 Copy-Paste-Texte: `google-sites/seiten/*.md`  
🔗 Play-Console-URLs: `google-sites/play-console-urls.txt`

## Seiten

| Datei | Zweck | Google Play |
|-------|-------|-------------|
| `index.html` | Landing Page, App-Beschreibung | Store Listing Support |
| `datenschutz.html` | Datenschutzerklärung (DSGVO) | **Privacy Policy URL** (Pflicht) |
| `nutzungsbedingungen.html` | AGB / Nutzungsbedingungen | Empfohlen |
| `konto-loeschen.html` | Kontolöschung Anleitung | **Account Deletion URL** (Pflicht bei Login) |
| `impressum.html` | Impressum (AT/DE) | Pflicht für EU |
| `kontakt.html` | Support-Kontakt | Play Console Support-E-Mail |

## Vor dem Veröffentlichen

1. **Impressum ausfüllen** – echte Adresse, Name/Firma, UID falls vorhanden
2. **E-Mail-Adressen ersetzen** – `@campshare.app` durch deine Domain (z. B. `@craftedcodelabs.com`)
3. **Google-Play-Link** in `index.html` aktualisieren, sobald die App live ist

## Google Play Console – URLs eintragen

Nach dem Hosting (siehe unten) diese URLs in der Play Console hinterlegen:

- **Datenschutzrichtlinie:** `https://DEINE-DOMAIN/datenschutz.html`
- **Konto löschen:** `https://DEINE-DOMAIN/konto-loeschen.html`
- **Website:** `https://DEINE-DOMAIN/`

### Data Safety Form (Orientierung)

In der Datenschutzerklärung dokumentiert:

- E-Mail, Profilname, Telefon (optional), Inserate, Chat, Fotos
- FCM-Token (Push)
- Advertising-ID (AdMob, Free-Tier)
- Kaufstatus (RevenueCat / Google Play)
- Drittanbieter: Supabase, Firebase, Google AdMob, RevenueCat, Google Play

## Hosting-Optionen

### Firebase Hosting (empfohlen – Projekt existiert bereits)

```bash
npm install -g firebase-tools
firebase login
cd website
firebase init hosting   # Public directory: . (current)
firebase deploy --only hosting
```

### GitHub Pages

Repository → Settings → Pages → Branch `main`, Folder `/website`

### Netlify

Ordner `website` als Publish Directory deployen.

## Lokal testen

```bash
cd website
python -m http.server 8080
# http://localhost:8080
```

## Struktur

```
website/
├── css/styles.css
├── index.html
├── datenschutz.html
├── nutzungsbedingungen.html
├── konto-loeschen.html
├── impressum.html
├── kontakt.html
└── README.md
```
