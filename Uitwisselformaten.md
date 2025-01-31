# Uitwisselformaten

**Op basis van de informatiemodellen worden uitwisselformaten gedefinieerd. Waar
een informatiemodel de semantiek bepaalt, beschrijft een uitwisselformaat de
vorm of syntax waarin geo-informatie op basis van een bepaald informatiemodel
wordt uitgewisseld. Er zijn verschillende manieren om geo-informatie te
representeren en uit te wisselen.**

## Overzicht geostandaarden uitwisselformaten

In het overzicht van geo-standaarden voor uitwisselformaten zijn de onderwerpen onderscheiden en in onderstaande tabellen opgenomen:

-   Uitwisselstandaarden voor het uitwisselen van vectordata (tabel 6.1);
-   Uitwisselstandaarden voor het uitwisselen van rasterdata (tabel 6.2);
-   Uitwisselstandaarden voor het uitwisselen van sensordata (tabel 6.3);
-   Uitwisselstandaarden voor het uitwisselen van 3D data (tabel 6.4).

## Vectordata uitwisselstandaarden

De vectorrepresentatie wordt gebruikt voor het vastleggen van discrete fenomenen
waarin de geometrie van een object wordt beschreven met behulp van primitieven
zoals: punt, lijn en vlak (2D) of met volvlakken (3D). De geometrische
basistypes voor vectorgegevens worden gedefinieerd in ISO 19107 middels een
geometrie model. In deze standaard worden ook primitieven gedefinieerd voor
topologisch modelleren waarbij de onderlinge relaties tussen geografische
objecten expliciet worden vastgelegd. ISO 19107 bevat een uitgebreid scala aan
geometrische types terwijl er in de praktijk doorgaans een zeer beperkte subset
gebruikt wordt. OGC heeft een subset, simple features profile, van ISO 19107
gedefinieerd die voor vrijwel alle toepassingen voldoende is. Ook binnen
Nederland is het simple features profile een zinnige inperking van ISO 19107.
Een uitzondering moet gemaakt worden voor cirkelbogen. Historisch worden veel
geo-objecten in Nederland met cirkelbogen beschreven terwijl cirkelbogen geen
deel uitmaken van het simple feature profile 3.1.1. Voor ISO 19136:2007 (GML
3.2.1) is er een simple features profile (OGC 10-100r3, 2011-05-24, version 2.0)
beschikbaar dat wel voldoet aan de eisen en wensen van Nederland (inclusief
bogen). Voor deze uitwisseling van vectordata bestaan de volgende standaarden (tabel 6.1).

*Tabel 6.1 – Uitwisselformaten standaarden en specificaties met betrekking tot vectordata*

| **Internationale standaarden/specificaties**                                                            | **Europese profielen**                                                                | **Nederlandse profielen**    |
|---------------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------------|------------------------------|
| ISO 19107 Geographic information - Spatial Schema [[ISO-19107-2003]]  | INSPIRE Guidelines for the encoding of spatial data [[inspire-gen]] |
| OGC Geography Markup Language (GML) Encoding Specification, version 3.1.1. [[GML31]]  |  |  |
| OGC Geography Markup Language (GML) Encoding standard, version 3.2.1 (=ISO 19136) [[iso-19136-2007]]  |  |  |
| OGC Geography Markup Language (GML) Encoding standard, version 3.3  [[GML33]]  |  |   |
| Simple Features profile (OGC 10-100r3, version 2.0) op ISO 19136:2007 (GML 3.2.1)  [[GMLSF]]  |  |  |
| OGC GeoPackage Encoding Standard, version 1.3.1 [[GeoPackage]]  | GeoPackage encoding of INSPIRE datasets. Inspire good practise. [[INSGPGeopackage]] |  |
| The GeoJSON Format [[rfc7946]] |  |  |
| OGC JSON Features and Geometries **draft** [[JSON-FG]]  |  |  |
| HTML5 [[html5]] |  |                              |
| Resource Description Framework (RDF): Concepts and Abstract Syntax. [[rdf11-concepts]]  |  |    |

## Rasterdata uitwisselstandaarden

<aside class="issue">Moeten we  in het raamwerk geostandaarden ook geen aandacht gaan besteden aan uitwisselformaten voor:
-	Reality data en mesh file formats: Pointclouds, Reality mesh, Photos (zie bijv,. https://communities.bentley.com/products/3d_imaging_and_point_cloud_software/w/wiki/59030/reality-data-formats-best-practices); vangen we dit domein helemaal af met Coverages en geotiff/NETCDF/…
-	M.bt. datacubes (voor science-achtige toepassingen); zie de sheet van Peter Bauman; ISO standaard voor SQL voor data arrays en update ISO standaard 19123-3? 
-	Cloudnative formats; geoparquet, STAC, … https://www.ogc.org/ogcevents/cloud-native-geospatial-outreach-event

Deze uitwisselformaten passen mogelijk bij de categorie Rasterdata. Dan is het niet nodig om er een nieuwe paragraaf voor te introduceren. Misschien wel om de titel aan te passen.

Zie deze tekst op de [ogc coverages DWG wiki](https://external.ogc.org/twiki_public/CoveragesDWG/WebHome):

> digital representations of space/time varying phenomena, concretely: spatio-temporal regular and irregular grids, point clouds, and general meshes. In particular, multi-dimensional datacubes fall under this category, such as 1-D sensor time series, 2-D satellite imagery, 3-D x/y/t image time series and x/y/z geoscientific models, 4-D x/y/z/t climate and ocean data sets, and more.

Op basis van die tekst zouden we onderstaande kunnen herschrijven als: 

De raster representatie wordt gebruik voor het vastleggen van fenomenen waarbij
aan ieder punt op het aardoppervlak een waarde uit een continu domein wordt
toegekend. *Het gaat daarbij over het algemeen om ruimtelijk-temporele gegevens, i.e. ieder punt heeft naast een waarde ook een tijdstip. Allerlei soorten bestanden vallen hieronder, bijvoorbeeld naast gewone rasterdata ook point clouds, meshes, en data cubes.*

In dat geval zouden we in deze paragraaf ook opnemen: 
- [Geoparquet](https://github.com/opengeospatial/geoparquet) (of is dit vector data?)
- [QB4ST: RDF Data Cube extensions for spatio-temporal components](https://www.w3.org/TR/qb4st/)
- [lAS](https://www.ogc.org/standards/LAS)
- ...?

</aside>

De raster representatie wordt gebruik voor het vastleggen van fenomenen waarbij
aan ieder punt op het aardoppervlak een waarde uit een continu domein wordt
toegekend. Voorbeelden zijn de luchtdruk boven Nederland, waardes van een
schadelijke stof, temperatuurswaarden of – zoals bij een foto reflectiewaarden.
In OGC en ISO/TC 211 termen heet dit een coverage. Zo’n coverage wordt vaak
geïmplementeerd door over het terrein een regelmatig grid van punten te leggen
(het raster) en voor ieder punt een waarde op te nemen. Deze waarde is
bijvoorbeeld een hoogteaanduiding bepaald middels laser altimetrie of de
numerieke codering van een kleurenwaarde opgenomen in een satellietbeeld.

Er zijn verschillende geostandaarden voor rasterdata opgenomen in het raamwerk (zie tabel 6.2),
zoals NETCDF en HDF5. Ook GeoTIFF (Geo Tagged Image File Format), waarbij
georeferentie als tags in de file is opgenomen. Daarnaast webstandaarden als JPEG2000 en PNG. De
laatste wordt vooral toegepast in WMS.

*Tabel 6.2 - Uitwisselformaten standaarden en specificaties met betrekking tot rasterdata*

| **Internationale standaarden/specificaties**                                         | **Europese profielen**                                          | **Nederlandse profielen** |
|--------------------------------------------------------------------------------------|-----------------------------------------------------------------|---------------------------|
| OGC Network Common Data Form (NetCDF) Core Encoding Standard version 1.0. [[NETCDF]] | INSPIRE Guidelines for the encoding of spatial data [[inspire-gen]]  |                           |
| Hierarchical Data Format 1.0 [[HDF5]]                                                |                                                                 |                           |
| HDF-EOS5 Data Model, File Format and Library (v1.1)        [[HDFEOS]]                |                                                                 |                           |
| OGC GeoTIFF Standard, version 1.1 [[GeoTIFF]]                                        |                                                                 |                           |
| ISO/IEC 15444-1:2019 - JPEG 2000 image coding system [[JPEG2000]]                    |                                                                 |                           |
| ISO 19123-1: Coverage Fundamentals [[iso-19123-2005]]                                |                                                                 |                           |
| ISO 19123-2: Coverage Implementation Schema (CIS 1.0) [[CIS10]]                      |                                                                 |                           |
| GML for JPEG 2000  [[GMLJPEG2000]]                                                   |                                                                 |                           |
| ISO/IEC 15948:2004 - Portable Network Graphics [[PNG]]                               |                                                                 |                           |
| CoverageJSON 1.0 **Draft** [[COVJSON]]                                               |                                                                 |                           |

## Sensordata uitwisselstandaarden

Met sensoren worden apparaten bedoeld voor het meten van stoffen in water,
grondsamenstellingen, grondwater, luchtverontreiniging, etc. Deze sensoren
hebben ook een positie en de resultaten van de metingen dienen uitgewisseld te
kunnen worden. Voor deze uitwisseling van observations en measurements bestaan
de volgende standaarden (tabel 6.3).

*Tabel 6.3 – Uitwisselformaten standaarden en specificaties met betrekking tot sensordata*

| **Internationale standaarden/specificaties**                                  | **Europese profielen**                                            | **Nederlandse profielen** |
|-------------------------------------------------------------------------------|-------------------------------------------------------------------|---------------------------|
| OGC Observations and Measurements version (ISO 19156) 3.0 **goedgekeurd, nog niet gepubliceerd** [[OMS3]]| INSPIRE Guidelines for the encoding of spatial data. [[inspire-gen]]| Informatiemodel Metingen [[IMMetingen]] |
| Observations and Measurements - XML Implementation 2.0[[OaMx2]]| | |
| W3C/OGC Semantic Sensor Network Ontology [[vocab-ssn]]                        |                                                                   |                           |
| OGC SensorML 2.1 [[SensorML]]                                                 |                                                                   |                           |

## 3D data uitwisselstandaarden

Met 3D data uitwisselstandaarden wordt de uitwisseling van 3-dimensionele data bedoeld, dat wil zeggen data over objecten en verschijnselen in de geografische ruimte, waarin de x-y en z-coordinaat zijn vastgelegd. Voor de uitwisseling van 3D data zijn de volgende standaarden beschikbaar (tabel 6.4).

*Tabel 6.4 – Uitwisselformaten standaarden en specificaties met betrekking tot 3D data*

| **Internationale standaarden/specificaties**                                   | **Europese profielen** | **Nederlandse profielen** |
|--------------------------------------------------------------------------------|------------------------|---------------------------|
| OGC City Geography Markup Language (CityGML) Encoding Standard, version 2.0 [[CityGML2]] |              |                           |
| CityJSON Community Standard, version 1.1.2 [[CityJSON]]                        |                        |                           |

## Kwaliteit en uitwisselformaten

**Validatie**

Een belangrijk kwaliteitsaspect van een uitwisselformaat is de mogelijkheid deze te valideren. Bij voorkeur gebeurt dit met geautomatiseerde processen, dan wel beschreven procedures en validatieregels. Validatie helpt om uitwisselformaten te laten voldoen aan de bij de geostandaard horende validatieregels. Om te helpen bij validatie zijn validatietools beschikbaar. De tools zijn bedoeld als hulpmiddel om fouten in de toepassing van standaarden te verminderen. 

Er zijn twee Nederlandse validators voor de validatie van GML (vectordata):
- De [GML3.2 Simple Features validator](http://validatie.geostandaarden.nl/gml/simple-features) controleert of een GML 3.2 bestand voldoet aan het GML 3.2 Simple Feature profile, level 2
- De [Validator voor GML 2D geometrie](http://validatie.geostandaarden.nl/gml/geometrie-2d) controleert of de 2D geometrieën in een GML 3.x bestand conform ISO 19107 (Spatial Schema) zijn.

**Handreiking Geometrie in model en GML**

De handreiking [Geometrie in model en GML](https://docs.geostandaarden.nl/nen3610/gimeg/) beschrijft de toepassing van geometrie in informatiemodellering en de implementatie daarvan in GML. Het is daarmee een ondersteuning voor de toepassing van de norm NEN 3610:2011 – Basismodel geo-informatie [NEN3610]. NEN 3610 gaat hierin niet verder dan verwijzing naar de relevante geo-informatie (ISO) normen. Voor het werkveld zijn deze normen niet toegankelijk genoeg om te kunnen toepassen. Middels deze handreiking wordt de brug gelegd. Dit document kan als een zelfstandig document worden gelezen. De inhoud is grotendeels gebaseerd op originele normen. Voor de toegankelijkheid is de tekst vertaald naar het Nederlands en bovendien vereenvoudigd. Deze handreiking kan daarom niet de normen vervangen, maar bijvoorbeeld als introductie worden gebruikt. Voor de normatieve referentie wordt in alle gevallen naar de originele documenten verwezen. 

**Handreiking lichte formaten geometrie**

Voor het uitwisselen van geodata kan je kiezen uit verschillende bestandsformaten. Wat het beste formaat is voor een toepassing, is afhankelijk van meerdere aspecten. In het bij de data behorende informatiemodel kunnen deze aspecten al naar voren komen - bijvoorbeeld de geometrietypes die worden vastgelegd, het gebruikte modelleerparadigma, etc. Echter kun je vanuit één informatiemodel ook weer meerdere implementaties in uitwisselingsformaten afleiden - beslissingen in het model sluiten dit niet per sé uit.

Daarom is voor vectorformaten een keuzehulp gemaakt: de handreiking [Geometrie in uitwisselingsformaten](https://docs.geostandaarden.nl/g4w/geox/). Deze legt ook de toepassing uit van de verschillende versies van GML. De handreiking lichte formaten geometrie [[HRLFG]] geeft handvaten voor het kiezen van het juiste formaat voor de juiste situatie, en geeft gedetaileerde informatie over het uitwisselen van geometrie in de lichte formaten HTML, GML, JSON, GeoPackage en RDF. Deze handreiking zet de belangrijkste aspecten op een rijtje en brengt deze in verband met gangbare toepassingen. De toepassing bepaalt namelijk wat de eisen aan de geometrieën zijn (zijn complexe types nodig? Is een hoge nauwkeurigheid van belang?), en welke verplichtingen aan de orde zijn in de keuze voor standaarden. De antwoorden op deze vragen kunnen al een indicatie geven van de geschiktheid van de formaten. Daarnaast is het van belang om inzicht te hebben in de behoeften van gebruikers: is ondersteuning in bepaalde tools/frameworks van belang? Moeten de bestanden leesbaar zijn voor mensen, en gemakkelijk te vinden? Hoe belangrijk is de semantiek van de data? Deze handreiking geeft handvaten voor het kiezen van het juiste formaat voor de juiste situatie, en geeft in afzonderlijke hoofdstukken gedetailleerde informatie over het uitwisselen van geometrie in GML, HTML, JSON, GeoPackage en RDF. 


