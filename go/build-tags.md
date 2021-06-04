# Build Tags

Go erlaubt mit sogenannten Build-Tags Dateien nur einzubinden, wenn man mit `--tags` das entsprechende Tag setzt.

In einem konkreten Fall habe ich einen Test, der nur in bestimmten Fällen ausgeführt werden soll, da er eine Abhängigkeit hat.

```go
    // +build integration
```

Dieses muss man an den Anfang der Datei schreiben und danach eine Leerzeile einfügen.

Nun kann man mit `go test --tags integration` die Tests der Datei mit einschließen.

## Boolsche Logik

Die Tags kann man mit AND und OR sowie NOT kombinieren. 

### OR - Oder

Oder lässt sich durch `// +build one two` realisieren, d.h. entweder der Tag one oder Tag two muss hier genutzt werden.


### AND - Und

Oder lässt sich durch `// +build one,two` realisieren, d.h. entweder der Tag one oder Tag two muss hier genutzt werden.
Auch separate Zeilen funktionieren:
```go
// +build one
// +build two
```

### NOT - Negation
Durch `!` kann man Negation- Logik realisieren. D.h., Dateien, die diesen Tag haben, werden dann eingebunden, wenn der Tag nicht vorhanden ist.

```go
// +build !one
```

Hier kann man auch sich ausschließende Bedingungen schaffen. Beispielsweise Integrationstest einbinden und Unit-Tests ausschließen. 

In den Integrationstests:
```go
// +build integration
```

In den Unittests
```go
// +build !integration.
```

Dann kann man mit `go test --tags integration` die Integrationstests ausführen und mit `go test` die Unit-Tests.





