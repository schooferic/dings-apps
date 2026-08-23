# Website für die Dings-Apps

Statische Seiten für GitHub Pages: Startseite, Datenschutzerklärung und Support –
jeweils auf Deutsch und Englisch. App Store Connect verlangt eine Datenschutz-URL
und eine Support-URL; beides wird von hier bedient.

## Veröffentlichen

1. Auf GitHub ein öffentliches Repository namens `dings-apps` anlegen.
2. Den Inhalt dieses Ordners hineinkopieren und pushen:

   ```bash
   git init && git add . && git commit -m "Website"
   git branch -M main
   git remote add origin https://github.com/schooferic/dings-apps.git
   git push -u origin main
   ```

3. Im Repository unter *Settings → Pages* als Quelle `main` / `/ (root)` wählen.

Die Seiten sind danach erreichbar unter:

| Zweck                     | URL                                                    |
|---------------------------|--------------------------------------------------------|
| Marketing-URL             | `https://<benutzername>.github.io/dings-apps/`          |
| Datenschutz (DE)          | `https://<benutzername>.github.io/dings-apps/datenschutz/` |
| Datenschutz (EN)          | `https://<benutzername>.github.io/dings-apps/privacy/`  |
| Support (DE)              | `https://<benutzername>.github.io/dings-apps/support/`  |
| Support (EN)              | `https://<benutzername>.github.io/dings-apps/support-en/` |

## Wenn dein Benutzername nicht `ericschoof` ist

Die Pfade in den Seiten sind auf ein Repository namens `dings-apps` ausgelegt und
funktionieren mit jedem Benutzernamen. Nur die Dateien unter `AppStore/metadata/`
enthalten die vollständigen URLs – dort den Benutzernamen anpassen:

```bash
grep -rl "schooferic.github.io" ../metadata | xargs sed -i '' 's/ericschoof/<benutzername>/g'
```

## Bei eigener Domain

Eine Datei `CNAME` mit der Domain anlegen und in den Seiten die Pfad-Präfixe
`/dings-apps` entfernen.
