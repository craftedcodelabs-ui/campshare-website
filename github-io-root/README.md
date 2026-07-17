# app-ads.txt auf GitHub Pages Stammdomain

AdMob sucht die Datei auf der **Stammdomain** deiner Entwickler-Website, nicht im Unterordner.

| Play Console Website | AdMob erwartet |
|----------------------|----------------|
| `https://craftedcodelabs-ui.github.io/campshare-website/` | `https://craftedcodelabs-ui.github.io/app-ads.txt` |

## Einmalig einrichten

1. Neues GitHub-Repository: **`craftedcodelabs-ui.github.io`** (Name exakt so)
2. Diese `app-ads.txt` ins Repo-Root legen (kein Unterordner)
3. **Settings → Pages → Branch `main` → Deploy**
4. Prüfen: https://craftedcodelabs-ui.github.io/app-ads.txt im Browser öffnen

Die CampShare-Website bleibt unverändert unter `/campshare-website/`.
