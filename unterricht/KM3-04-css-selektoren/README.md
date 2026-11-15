# KM3-04 – CSS-Selektoren

## Beispiel 1

Die [erweiterte Demo](demo.html#speisekarte) verwendet diese Selektoren:

| Ziel | Selektor |
| --- | --- |
| Kopfzeile | `#speisekarte thead` |
| Jede zweite Datenzeile | `#speisekarte tbody tr:nth-child(even)` |
| Linker Rand beim letzten Eintrag | `#speisekarte tbody tr:last-child td:first-child` |
| Zweiter Schritt | `#speisekarte ol > :nth-child(2)` |
| Vorletzter Schritt | `#speisekarte ol > :nth-last-child(2)` |
| Kasten mit Bild | `#speisekarte .kasten:has(img)` |

`:has(img)` prüft, ob der Kasten ein Bild enthält. `:is(img)` prüft, ob das ausgewählte Element selbst ein Bild ist.

## Beispiel 2

- [x] `p.hinweis` trifft Absätze mit der Klasse `hinweis`.
- [x] `h2 ~ p` trifft spätere Absätze mit demselben Elternelement wie die Überschrift.
- [ ] `:nth-child(2)` und `:nth-of-type(2)` treffen immer dasselbe Element.
- [x] Bei gleichem Gewicht gewinnt die später notierte Regel, wenn auch die übrigen Kaskadenbedingungen gleich sind.

Bei `<h3>…</h3><p>Erster Absatz</p><p>Zweiter Absatz</p>` trifft `p:nth-child(2)` den ersten Absatz. `p:nth-of-type(2)` trifft den zweiten Absatz, weil nur die Absätze gezählt werden.

| Ziel | Selektor |
| --- | --- |
| Links auf PDF-Dateien | `a[href$=".pdf"]` |
| Absätze ohne die Klasse `hinweis` | `p:not(.hinweis)` |
| Erstes Listenelement in jeder ungeordneten Liste | `ul > li:first-of-type` |
| Jedes Element, das ein Bild enthält | `:has(img)` |
| Aktivierte Checkbox direkt vor einem Label | `input[type="checkbox"]:checked:has(+ label)` |

`p:nth-child(1)` trifft nur einen Absatz, der zugleich das erste Kind ist. `p:first-of-type { font-weight: bold; }` trifft den ersten Absatz auch dann, wenn eine Überschrift davor steht.

## Beispiel 3

Die [CSS-Lösung](loesung.css) ist in [transfer.html](transfer.html) eingebunden.

Das Attribut `data-topic` steht bereits im HTML und beschreibt das Thema der Sektion. Der Präfix-Selektor erfasst alle Sektionen im Testbereich, deren Thema mit `css-adv` beginnt.
