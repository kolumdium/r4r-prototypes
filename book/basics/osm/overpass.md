# Overpass und Overpass Turbo

Overpass ist eine Abfragesprache für OpenStreetMap-Daten. Sie wird verwendet, um Daten aus der OpenStreetMap-Datenbank zu extrahieren. Overpass Turbo ist ein Web-basierter Dienst, der Overpass-Abfragen ausführt und die Ergebnisse auf einer Karte anzeigt.

[https://wiki.openstreetmap.org/wiki/Overpass_API](https://wiki.openstreetmap.org/wiki/Overpass_API)
[https://overpass-turbo.eu](https://overpass-turbo.eu)

## Wie man Overpass Queries schreibt

Ein Overpass-Query besteht aus drei Teilen:

1. **Global Settings** `[out:json]` gibt das Format der Ausgabe an. Es kann auch `xml` oder `csv` sein. `[timeout:25]` gibt die maximale Laufzeit der Abfrage in Sekunden an. `[bbox\:30.618338,-96.323712,30.591028,-96.330826]` gibt den Bereich der Abfrage an.
2. **Filter**: Die Abfrage kann aus verschiedenen Filtern zusammengestellt werden. Mit nwr\["key"="value"\] werden alle Nodes, Ways und Relations mit dem Tag "key"="value" ausgewählt.
    - Verknüpfungen mit UND werden durch zwei Filter abgebildet: nwr\["key"="value"\]\["key"="value"\]
    - Verknüpfungen mit ODER werden durch ein Semikolon abgebildet: nwr\["key"="value"\];nwr\["key"="value"\]
    - Negationen werden durch ein Ausrufezeichen abgebildet: nwr\["key"!="value"\]
    - Im Overpass Turbo Wizard können Reguläre Ausdrücke mit `~` verwendet werden: nwr\["key"~"value"\]
    - In Overpass Turbo gibt ({{bbox}}) die aktuelle Ansicht der Karte an.
3. **Ausgabe**: Was Ausgegeben werden soll. In der Regel wird `out geom;` verwendet.

Ausgabe ist ähnlich wie bei [https://wiki.openstreetmap.org/wiki/Overpass_API/Overpass_QL](https://wiki.openstreetmap.org/wiki/Overpass_API/Overpass_QL) aber out geom; ist spezifisch für Overpass Turbo.

One of the following for the degree of verbosity of the output; the default is out body:

- out ids: Print only the ids of the elements in the set.
- out skel: Print the minimum information necessary for geometry:
  - for nodes: id and coordinates
  - for ways: id and the ids of its member nodes
  - for relations: id of the relation, and the id, type, and role of all of its members.
- out body: Print all information necessary to use the data. These are also tags for all elements and the roles for relation members.
- out tags: Print only ids and tags for each element and not coordinates or members.
- out meta: Print everything known about the elements. meta includes everything output by body for each OSM element, as well as the version, changeset id, timestamp, and the user data of the user that last touched the object. Derived elements' metadata attributes are also missing for derived elements.
