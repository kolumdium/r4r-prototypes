# OSM Tags

OSM besteht im wesentlichen aus 3 Arten von Elementen: Nodes, Ways und Relations. Jedes dieser Elemente kann Tags haben, die zusätzliche Informationen enthalten. Tags bestehen aus einem Schlüssel und einem Wert. Tags können auch mehrfach vorkommen.
Mehr Infos dazu findet man im [OSM Wiki#Tags](https://wiki.openstreetmap.org/wiki/Tags).
Um die zu finden, welche Key und Value Kombinationen in OSM verwendet werden sollte zuerst das Wiki durchsucht werden. Es gibt eigentlich immer eine preferierte Kombination. Zwar gibt es keinen "offiziellen" Tag, aber es gibt Tags, die von der Community bevorzugt werden. Diese sind in der Regel auch besser dokumentiert.
Um herrauszufinden, welche Tags tatsächlich verwendet werden kann unter anderem [Taginfo](https://taginfo.openstreetmap.org/) verwendet werden.

## Mehrfachwerte und Subtags

Tags können auch Subtags haben. z.B. sidewalk:left:width. Das bedeutet, dass der Gehweg auf der linken Seite eine bestimmte Breite hat. Es gibt auch Tags, die mehrere Werte haben können. z.B. access=private;no. Das bedeutet, dass der Zugang nur für Personen mit einem Schlüssel und nicht für Personen ohne Schlüssel erlaubt ist.
Werte werden von jedem Mapper "interpretiert" und können daher auch unterschiedlich sein. Es gibt auch Tags, die nur in bestimmten Ländern verwendet werden. z.B. [DE:](https://wiki.openstreetmap.org/wiki/DE:Key:access) oder [AT:](https://wiki.openstreetmap.org/wiki/AT:Key:access).
So entstehen z.B. Key-Value Paare wie sidewalk:left:width=1.5m oder sidewalk:both:width=1.5;1.6. 
Zwar sind solche Kombinationen selten, aber dennoch immerwieder anzutreffen.

(unsere-tags)=
## Unsere Tags

Für eine Reproduzierbarkeit und Vergleichbarkeit der Analysen werden die verwendeten Tags hier aufgelistet. Findet Ihr fehler oder haben wir ein Tag vergessen, dann schreibt uns bitte eine Mail an [info@ready-for-robots.de](mailto:info@ready-for-robots.de).
Es wurde bei der Auswahl entschieden, dass nicht 100% aller Values betrachtet werden müssen. Seltene Tags wurden einfach ignoriert. Das könnt Ihr gerne verbessern.

```Yaml
[Tags]
    [[NotNo]]
    # List of commonly used tags that are inclusive
        notno = '''
            yes
            left
            right
            both
            sperate
            shared
            lane
            sidepath
            footway
            share_busway
        '''

    [[UsefulTagsWay]]
    # osmtags to download
    # It will add all used tags in the filters i.e. cyclestreet
    # and the once listed below
        usefultagsway = '''
            bride
            tunnel
            oneway
            lanes
            ref
            name
            highway
            maxspeed
            service
            access
            area
            landuse
            width
            est_width
            junction
            surface
            smoothness
            lanes:width
            lanes:surface
            lanes:smoothness
        '''

    # Following are the categories used to calculate the usage and speeds.
    # the categories consist of key = value pairs
    # each of which will be translated to osm tags.

    [[Intercity]]
        highway = '''
            primary
            secondary
        '''
    [[Local]]
        highway = '''
            tertiary
            living_street
            residential
            service
            unclassified
        '''
    [[Bicycle]]
        highway ='''
            cycleway
            path
            service
            track
        '''
        cycleway = '''
            lane
            track
            opposite
            shared_lane
            asl
            opposite_lane
            seperate
            share_busway
            sidepath
            right
            left
            both
            sidewalk
            segregated
            both
            opposite_track
            cyclestreet
        '''
        bicycle = '''
            yes
            designated
            use_sidepath
            permissive
            official
        '''
        cyclestreet ='''
            yes
        '''
        extra_tags ='''
            cycleway:right
            cycleway:left
            cycleway:both
        '''
    [[Sidewalk]]
        highway = '''
            pedestrian
            footway
            path
            living_street
        '''
        path = '''
            sidewalk
            sidepath
        '''
        footway ='''
            sidewalk
            crossing
        '''
        sidewalk ='''
            yes
            right
            left
            both
            seperate
            both
            shared
        '''
        foot = '''
            yes
            designated
            permissive
        '''
        extra_tags ='''
            sidewalk:right
            sidewalk:left
            sidewalk:both
        '''
    [[Overrides]]
        [[[Living_street]]]
            highway ='''
                living_street
            '''
```
