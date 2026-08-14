# Blog-Grundgerüst (Hugo)

## Was ist drin

- `hugo.toml` – Konfiguration (Blogname, Menü) – **hier zuerst `baseURL` und `title` anpassen**
- `content/_index.md` – Startseiten-Text
- `content/posts/open-source-software-empfehlungen.md` – dein erster Artikel als Vorlage
- `content/about.md`, `content/impressum.md`, `content/datenschutz.md` – feste Seiten, **unbedingt vor Veröffentlichung ausfüllen**
- `.github/workflows/hugo.yml` – baut die Seite automatisch bei jedem Push und veröffentlicht sie

## Schritt für Schritt live schalten

1. **Neues GitHub-Repo erstellen** (z.B. `mein-blog`), öffentlich, ohne README/gitignore vorauswählen.

2. **Diesen Ordner in das Repo pushen:**
   ```bash
   cd blog
   git init
   git add .
   git commit -m "Initial commit"
   git branch -M main
   git remote add origin https://github.com/DEIN-USERNAME/DEIN-REPO-NAME.git
   git push -u origin main
   ```

3. **Theme als Submodule hinzufügen** (PaperMod – schlichtes, gutes Blog-Theme):
   ```bash
   git submodule add https://github.com/adityatelange/hugo-PaperMod.git themes/PaperMod
   git submodule update --init --recursive
   git add .
   git commit -m "Add PaperMod theme"
   git push
   ```

4. **`hugo.toml` anpassen:** `baseURL` auf `https://DEIN-USERNAME.github.io/DEIN-REPO-NAME/` setzen, `title` auf deinen Blognamen. Committen und pushen.

5. **GitHub Pages aktivieren:** Im Repo unter *Settings → Pages → Source* auf **"GitHub Actions"** stellen (nicht "Deploy from branch").

6. **Fertig.** Nach ein bis zwei Minuten ist die Seite unter `https://DEIN-USERNAME.github.io/DEIN-REPO-NAME/` live. Jeder weitere `git push` auf `main` aktualisiert sie automatisch.

## Lokal testen (optional, aber praktisch)

Falls du Hugo lokal installierst (https://gohugo.io/installation/), kannst du vor dem Push lokal prüfen:
```bash
hugo server -D
```
Öffnet die Seite unter `http://localhost:1313` mit Live-Reload.

## Vor der Veröffentlichung nicht vergessen

- [ ] `content/impressum.md` ausfüllen (echte Adresse oder c/o-Adresse eines Anbieters)
- [ ] `content/datenschutz.md` an tatsächlich genutzte Dienste anpassen
- [ ] `content/about.md` ausfüllen
- [ ] Platzhaltertexte im Open-Source-Artikel durch echten Inhalt ersetzen
