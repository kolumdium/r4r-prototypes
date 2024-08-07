# Begrifflichkeiten und Erklärungen

In diesem Abschnitt erklären wir die Begriffe, die wir in unseren Analysen und Visualisierungen verwenden.

(beschreibung-szenarien)=
## Beschreibung Szenarien

Kurze Zusammenfassung was die Szearien abbilden die wir öfter nutzen.
Eine genaue Beschreibung ist im Paper "Ready for robots? Assessment of autonomous delivery robot operative accessibility in German cities." zu finden. {cite}`plank2022`

Wichtig hierfür ist auch die verwendeten Tags. Siehe [unsere-tags](unsere-tags).

| OSM Tag                     | highway                                                       | others                                                                                                         |
|-----------------------------|---------------------------------------------------------------|----------------------------------------------------------------------------------------------------------------|
| Collector streets           | primary, secondary                                            |  |
| Local streets               | tertiary, service, living\_street, residential,  unclassified |  |
| Bike lanes                  | cycleway, path, service, track                                | cycleway = \* , bicylce = \* , :(left and right and both) = \*, cyclestreet = yes |
| Sidewalks, pedestrian areas | Pedestrian areas, pedestrian, footway, path,  living\_street  | sidewalk = \*, foot = \* :(left and right and both) = \*, footway = sidewalk, crossing, path = sidewalk, sidepath |

| Scenario | Collector | Local   | Bike lanes | Pedestrian tracks |
|----------|-----------|---------|------------|-------------------|
| O1       | 40 km/h   | 20 km/h | 15 km/h    | 5 km/h            |
| L1       | 40 km/h   | 20 km/h | NO         | NO                |
| M1       | NO        | 20 km/h | 15 km/h    | 5 km/h            |
| M2       | NO        | NO      | 15 km/h    | 5 km/h            |
| S1       | NO        | NO      | NO         | 5 km/h            |

### Small

Aka S1

- Nur Fußgängerzonen und Gehwege

### Medium

Aka M1

- Fußgängerzonen und Gehwege
- Radwege
- Nebenstraßen

### Medium-restricted

Aka M2

- Fußgängerzonen und Gehwege
- Radwege

### Large

Aka L1

- Hauptstraßen
- Nebenstraßen

### Optimal

Aka O1 (Alles was von den ausgewählten Tags erfasst werden kann)

- Hauptstraßen
- Nebenstraßen
- Radwege
- Fußgängerzonen und Gehwege
