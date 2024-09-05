# ls

Wir bekommen alle Dateien und Verzeichnisse im Home-Verzeichnis aufgelistet.

Die gleiche Ausgabe in detailierter Form erhalten wir mit:

```bash
ls -l
```
Das -l ist eine Option. Es steht hier für eine "lange" Ausgabe - zu jeder Datei bekommen wir Informationen über Größe und Dateirechte

Verzeichnis "Downloads" ausgeben:

```bash
ls Downloads
```

Den Inhalt aller Verzeichnisse ausgeben:

```bash
ls *
```

Auch versteckte Dateien ausgeben:

```bash
ls -a
```

Auch versteckte Dateien ohne . und .. ausgeben:

```bash
ls -A
```

Optionen können wir auch kombinieren. Nach dem Minus müssen sie nur aneinandergereiht werden:

```bash 
ls -lA
```