# Sternschnuppen fangen ⭐

Ein kleines Tipp-Spiel für's Handy: Sternschnuppen fangen, Müll liegen lassen –
und am Ende jeder Runde zählen, wie viele man erwischt hat.

Läuft komplett im Browser, ohne Server und ohne Build-Schritt.
Gehostet über GitHub Pages.

## Spielen

* Online: GitHub Pages URL des Repos öffnen.
* **Als App installieren:** im Browser „Zum Home-Bildschirm hinzufügen“.
  Danach startet das Spiel im Vollbild ohne Browserleiste und funktioniert
  auch **offline** (Service Worker).

## Spielprinzip

| Symbol | Bedeutung |
| --- | --- |
| ⭐ | antippen und einsammeln |
| 🏀 💧 🍕 | nicht antippen – kostet ein Leben |
| 🦄 | Extraleben |
| ❄️ | alles wird 10 s langsamer |
| 🔥 | 5 s schnell, danach +2 Leben |
| 🌈 | sammelt alle Sterne auf dem Bildschirm ein |

Am Ende jeder Runde fliegen die gefangenen Sternschnuppen nach oben und man
tippt ein, wie viele es waren. Richtig = weiter, falsch = ein Leben weniger.

Drei Schwierigkeitsstufen (🐣 Leicht / 🐰 Mittel / 🦄 Schwer) steuern Tempo,
Anteil der Störobjekte und Rundenlänge. Pro Stufe wird ein eigener Rekord
gespeichert.

## Dateien

```
index.html            komplettes Spiel (HTML + CSS + Canvas-JS, keine Abhängigkeiten)
manifest.webmanifest  Web-App-Manifest (Installation, Icon, Vollbild)
sw.js                 Service Worker (Offline-Betrieb)
icons/                App-Icons (192/512 px, maskable, apple-touch-icon)
.nojekyll             GitHub Pages soll nichts an den Dateien verändern
```

## Entwickeln

`index.html` einfach im Browser öffnen. Für Service Worker und Installation
wird http(s) gebraucht, z. B.:

```sh
python3 -m http.server 8000
# dann http://localhost:8000 aufrufen
```

Nach Änderungen an den Dateien in `sw.js` die `CACHE_VERSION` hochzählen,
damit installierte Geräte die neue Version sicher bekommen.
