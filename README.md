# shx-ui — Ausweichquelle

Dieses Repo enthält die **ausgelieferten Dateien** der SHX-Bausteinsammlung. Es ist eine
Kopie, keine Quelle: Der Quelltext liegt privat in
[`SHX-Solutions/shx-ui`](https://github.com/SHX-Solutions/shx-ui).

## Wozu

Die Sammlung wird normalerweise über **`cdn.shx-solutions.com`** ausgeliefert — ein
Verzeichnis auf einem eigenen Server. Fällt der aus, wären alle Seiten, die das
Stylesheet per `<link>` einbinden, schlagartig ungestylt.

Deshalb liegt hier eine zweite Kopie, ausgeliefert über GitHub Pages. Sie springt ein,
wenn die erste nicht antwortet — mehr nicht. **Vorsorge, kein Ersatz.**

## Einbinden

```html
<link rel="stylesheet"
      href="https://cdn.shx-solutions.com/shx-ui/v1/shx-ui.min.css"
      onerror="this.onerror=null;this.href='https://shx-solutions.github.io/shx-ui-cdn/v1/shx-ui.min.css'">
<script src="https://cdn.shx-solutions.com/shx-ui/v1/shx-ui.js" defer
        onerror="this.onerror=null;this.src='https://shx-solutions.github.io/shx-ui-cdn/v1/shx-ui.js'"></script>
```

Für React-Projekte ist das nicht nötig: Dort kommt das Paket `@shx-solutions/ui` aus der
privaten Registry, und das Stylesheet steckt im Build.

## Was hier liegt

| Pfad | Inhalt |
|---|---|
| `<version>/` | eine feste Version, ändert sich nie |
| `v1/` | die jeweils neueste Ausgabe der Reihe 1 |
| `latest/` | die neueste überhaupt |

Je Ordner: `shx-ui.min.css`, `shx-ui.js`, `version.json`.

Die unminifizierte `shx-ui.css` liegt **nicht** hier, sondern nur auf dem eigenen Server.
Sie trägt fast 250 Zeilen Kommentar mit internen Notizen zu Gestaltungsentscheidungen — im
Notfall lädt eine Seite ohnehin die minifizierte Fassung.

## Hier wird nichts von Hand geändert

Der Inhalt entsteht bei jedem Release automatisch (`scripts/release-cdn.sh` im
Quell-Repo). Eine Änderung hier würde beim nächsten Release überschrieben — und wäre
schlimmer als nutzlos, weil sie die Ausweichquelle von der echten abweichen ließe.

## Warum öffentlich

Damit GitHub Pages es ausliefern kann. Das ist unbedenklich: Ein Stylesheet ist ohnehin
öffentlich, sobald eine Seite es benutzt. Der Quelltext, die React-Bausteine und das
npm-Paket bleiben privat.
