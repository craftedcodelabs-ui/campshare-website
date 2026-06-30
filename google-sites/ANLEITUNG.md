# CampShare in Google Sites einrichten

Google Sites lässt sich **nicht per HTML-Upload** befüllen – du erstellst die Seiten im Browser-Editor. Alle Texte liegen fertig zum Kopieren unter `seiten/`.

**Zeitaufwand:** ca. 30–45 Minuten

---

## Schritt 1: Neue Site anlegen

1. Öffne [sites.google.com](https://sites.google.com)
2. Klicke **Leer** (oder **Galerie** → Theme „Diplomat“ / „Impression“)
3. Seitentitel oben: **CampShare**
4. Untertitel: *Teilen · Tauschen · Helfen*

### Design (optional, passend zur App)

| Einstellung | Wert |
|-------------|------|
| Theme | Diplomat oder Impression |
| Farbe | Blau `#1D4ED8` oder `#0EA5E9` |
| Schrift | Roboto oder Open Sans |

---

## Schritt 2: Seitenstruktur anlegen

Rechts auf **Seiten** → für jede Zeile **+ Seite hinzufügen**:

| Seitenname (in Sites) | URL-Slug (automatisch) | Inhalt aus Datei |
|----------------------|------------------------|------------------|
| Start | `/` (Startseite) | `seiten/01-startseite.md` |
| Datenschutz | `/datenschutz` | `seiten/02-datenschutz.md` |
| Nutzungsbedingungen | `/nutzungsbedingungen` | `seiten/03-nutzungsbedingungen.md` |
| Konto löschen | `/konto-loeschen` | `seiten/04-konto-loeschen.md` |
| Impressum | `/impressum` | `seiten/05-impressum.md` |
| Kontakt | `/kontakt` | `seiten/06-kontakt.md` |

**Tipp:** Seiten per Drag & Drop unter „Start“ einrücken → erscheinen in der Navigation.

---

## Schritt 3: Inhalte einfügen

### Kurze Seiten (Start, Kontakt, Impressum)

1. Seite in Sites öffnen
2. Gesamten Text aus der `.md`-Datei markieren und kopieren
3. In den Seitenbereich einfügen (Strg+V)
4. Überschriften ggf. mit dem **Überschriften-Stil** (H2/H3) formatieren

### Lange Seiten (Datenschutz, AGB, Konto löschen) – empfohlen via Google Docs

1. [docs.google.com](https://docs.google.com) → **Neues Dokument**
2. Inhalt aus `seiten/02-datenschutz.md` einfügen
3. Überschriften formatieren (Format → Absatzformat → Überschrift 1/2)
4. In Google Sites: **Einfügen → Google Docs → Dokument auswählen**
5. Vorteil: einfacher zu bearbeiten, Tabelle in Datenschutz bleibt übersichtlich

### Tabelle (Datenschutz, Abschnitt 3)

In Google Docs: **Einfügen → Tabelle** (3 Spalten, 8 Zeilen) und Werte aus der Markdown-Tabelle übernehmen.

---

## Schritt 4: Navigation & Footer

1. **Seiten**-Panel: Reihenfolge = Start, Datenschutz, Nutzungsbedingungen, Konto löschen, Impressum, Kontakt
2. Auf der Startseite unten einen **Button-Bereich** einfügen:
   - Button „Google Play“ → Link zur Play-Store-URL (wenn live)
   - Button „Datenschutz“ → interne Seite Datenschutz
3. Auf jeder Seite am Ende optional Textblock:
   `© 2026 CampShare · Datenschutz | AGB | Konto löschen | Impressum | Kontakt` (jeweils als Link zur Site-Seite)

---

## Schritt 5: Veröffentlichen

1. Oben rechts **Veröffentlichen**
2. Webadresse wählen, z. B. `campshare` → URL wird:
   `https://sites.google.com/view/campshare`
3. Sichtbarkeit: **Jeder im Internet** (Pflicht für Google Play)
4. **Veröffentlichen** bestätigen

### Optionale eigene Domain

Google Sites → **Einstellungen** (Zahnrad) → **Benutzerdefinierte URLs**  
(Domain muss bei Google Search Console verifiziert sein, z. B. `www.campshare.app`)

---

## Schritt 6: URLs in Google Play Console

Nach dem Veröffentlichen diese URLs eintragen (Platzhalter `campshare` durch deinen Slug ersetzen):

```
Website:              https://sites.google.com/view/campshare
Datenschutzrichtlinie: https://sites.google.com/view/campshare/datenschutz
Konto löschen:        https://sites.google.com/view/campshare/konto-loeschen
Support-E-Mail:       support@DEINE-DOMAINE.com
```

### Wo in der Play Console?

| Feld | Pfad |
|------|------|
| Datenschutzrichtlinie | App-Inhalt → Datenschutzrichtlinie |
| Konto löschen | App-Inhalt → Sicherheit der Daten → Kontolöschung |
| Website | Store-Eintrag → Kontaktdetails → Website |

---

## Schritt 7: Pflicht-Anpassungen vor Go-Live

- [ ] **Impressum** – echte Adresse und Name eintragen (`seiten/05-impressum.md`)
- [ ] **E-Mail-Adressen** – `@campshare.app` durch echte Domain ersetzen (alle Seiten)
- [ ] **Google-Play-Link** auf der Startseite aktualisieren
- [ ] Alle Seiten im **Inkognito-Fenster** testen (öffentlich erreichbar?)

---

## Alternative: Statische HTML-Seite einbetten

Nur wenn du die HTML-Version behalten willst (z. B. auf Firebase gehostet):

1. HTML-Seiten deployen (siehe `website/README.md`)
2. In Google Sites: **Einfügen → Einbetten → URL** oder **Einbettungscode**
3. **Nicht empfohlen** für Datenschutz/Kontolöschung – Google Play erwartet den vollständigen Text direkt auf der verlinkten Seite, nicht nur in einem iframe.

**Empfehlung:** Inhalte nativ in Google Sites (Copy & Paste aus `seiten/`).

---

## Checkliste Google Play Richtlinien

- [x] Datenschutzerklärung (öffentliche URL)
- [x] Kontolöschung (eigene Seite mit Schritten)
- [x] Impressum / Kontakt
- [x] Nutzungsbedingungen
- [x] Haftungsausschluss (inoffizielles Community-Projekt)
- [x] In-App-Käufe & Werbung dokumentiert
- [x] Drittanbieter (Supabase, Firebase, AdMob, RevenueCat) genannt
