# **Awesome OGC SensorThings API** [![Awesome](https://awesome.re/badge.svg)](https://github.com/lkcozy/awesome-sensorthings-api)

A collection of awesome things regarding OGC SensorThings API(STA) ecosystem.

- [**Awesome OGC SensorThings API** ](#awesome-ogc-sensorthings-api-)
  - [OGC SensorThings API](#ogc-sensorthings-api)
  - [General Resources](#general-resources)
  - [Standard Specification](#standard-specification)
  - [Sandbox Services](#sandbox-services)
  - [Tools](#tools)
  - [Custom Extensions](#custom-extensions)
  - [Best Practices](#best-practices)
  - [Use Cases](#use-cases)
  - [Tutorials](#tutorials)
  - [Presentations](#presentations)
  - [Videos](#videos)
  - [Related Standards](#related-standards)
  - [Publications](#publications)

## OGC SensorThings API

> A standard providing an open and unified framework to interconnect IoT sensing devices, data, and applications over the Web.
> The SensorThings API is an open standard, builds on Web protocols and the OGC Sensor Web Enablement standards, and applies an easy-to-use REST-like style.

## General Resources

- [OGC SensorThings API Page](https://www.ogc.org/standards/sensorthings)
- [Online Documentation v1.0](https://developers.sensorup.com/docs/#introduction)
- [GitHub](https://github.com/opengeospatial/sensorthings)
- [Wiki Page](https://en.wikipedia.org/wiki/SensorThings_API)
- [SensorUp SensorThings API Documentation](https://developers.sensorup.com/docs/#introduction)
- [SensorThings API HowTo](https://fraunhoferiosb.github.io/FROST-Server/sensorthingsapi/1_Home.html)

## Standard Specification

- [Part 1: Sensing(2016)](http://docs.opengeospatial.org/is/15-078r6/15-078r6.html): Management and reception of observations or measurements made by IoT sensors
- [SensorThings API Part 1: Sensing 1.1(2021)](https://docs.ogc.org/is/18-088/18-088.html) ([PDF version](https://docs.ogc.org/is/18-088/18-088.pdf))
- [Part 2: Tasking Core(2019)](http://docs.opengeospatial.org/is/17-079r1/17-079r1.html): Tell the sensor/actuator what to do
- Part 3: Rules Engine: TBD
- Part 4: Tasking Extensions: TBD

## Sandbox Services

- [Fraunhofer IOSB v1.1](https://ogc-demo.k8s.ilt-dmz.iosb.fraunhofer.de/v1.1/)
- [SensorUp Toronto Bike v1.0](https://toronto-bike-snapshot.sensorup.com/display/v1.0)

## Tools

- [SensorUp STA Interactive SDK](https://developers.sensorup.com/InteractiveSDK/): A fun and easy way to learn how to use the OGC SensorThings API.
- [SensorUp STA Dashboard](http://dashboard-demo.sensorup.com/): STA Dashboard
- [SensorUp STA Browser](http://map-dashboard.sensorup.com/components/settings/index.html): STA Browser
- [SensorUp STA EXplorer](https://explorer.sensorup.com/?url=https://toronto-bike-snapshot.sensorup.com/v1.0):Generic visualization dashboard for SensorThings
- [SensorUp STA Share](https://share.sensorup.com/): Create and share snippets of code to showcase SensorThings
- [FROST-Server](https://github.com/FraunhoferIOSB/FROST-Server):The FRaunhofer Opensource SensorThings-Server is the first complete, open-source implementation of the OGC SensorThings API Part 1: Sensing
- [FROST-GeoJSON-Importer](https://github.com/hylkevds/FROST-GeoJsonImporter): A tool for importing GeoJSON FeatureCollections as Locations & Things into a SensorThings API compatible service.
- [Frost-Client](https://github.com/FraunhoferIOSB/FROST-Client): a Java-based client library for the SensorThingsAPI and aims to simplify development of SensorThings enabled client applications.
- [SensorThings API Python Client](https://pypi.org/project/frost-sta-client/#/): a client library to facilitate interaction with a FROST SensorThingsAPI Server
- [Geodan SensorThings .NET SDK](https://github.com/gost/sensorthings-net-sdk) : makes it easy to add OGC SensorThings support to your .NET application.
- [stapy](https://github.com/zMoooooritz/stapy): An easy to use SensorThings API Client written in Python
- [sensor-things-server](https://github.com/PAR-Government/sensor-things-server): Implementation of OGC SensorThings server in .NET that is suitable for being embedded into Xamarin
- 🐳 [sensorcamp-munich](https://github.com/lrswss/sensorcamp-munich): Docker stack to setup a LoRaWAN infrastructure including a FROST-Server on a Raspberry Pi
- [Grafana OGC SensorThings Plugin](https://grafana.com/grafana/plugins/linksmart-sensorthings-datasource/): This plugin enables the visualization of sensor and location data from an OGC SensorThings server on Grafana.
- [STAM (SensorThings API Map)](https://github.com/DataCoveEU/STAM): The JS library for showing the Things/Features of interest of a SensorThings server on a Leaflet/OpenLayers map.

## [Custom Extensions](https://github.com/opengeospatial/sensorthings/discussions/146)

> STA enables custom extensions since v1.1

- [CSV-ResultFormat](https://github.com/INSIDE-information-systems/SensorThingsAPI/blob/master/CSV-ResultFormat/CSV-ResultFormat.md): Adds a `$resultFormat=CSV` to get results in CSV format
- [GeoJSON-ResultFormat](https://fraunhoferiosb.github.io/FROST-Server/extensions/GeoJSON-ResultFormat.html): Adds a `$resultFormat=GeoJSON` to get results in GeoJSON format
- [EntityLinking](https://github.com/INSIDE-information-systems/SensorThingsAPI/blob/master/EntityLinking/Linking.md): Adds custom entity links (links between arbitrary entities, that can be used in $expand and $filter
- [OpenAPI](https://fraunhoferiosb.github.io/FROST-Server/extensions/OpenAPI.html): Adds a `/vx.y/api` path with an OpenAPI document
- [DeepSelect](https://fraunhoferiosb.github.io/FROST-Server/extensions/DeepSelect.html): Adds the ability to `$select` into complex properties.
- [SelectDistinct](https://fraunhoferiosb.github.io/FROST-Server/extensions/SelectDistinct.html): Adds the ability to select all different existing values of (a set of) properties
- [JsonBatchRequest](https://fraunhoferiosb.github.io/FROST-Server/extensions/JsonBatchRequest.html): Adds OData JSON batch requests, as an easier-to-use alternative to the Multipart batch requests.
- [ResponseMetadata](https://fraunhoferiosb.github.io/FROST-Server/extensions/ResponseMetadata.html): Adds the ability to reduce or extend the returned metadata for responses

## Best Practices

- [OGC Best Practice for using SensorThings API with Citizen Science](https://portal.ogc.org/files/100891)

## Use Cases

- [Sensor In Rooms](https://github.com/opengeospatial/sensorthings/blob/master/use-cases/SensorsInRooms.md)
- [Lead in Liver In Fishing River](https://github.com/opengeospatial/sensorthings/blob/master/use-cases/LeadInLiverInFishInRiver.md)

## Tutorials

- [SensorUp Mapping with SensorThings](https://developers.sensorup.com/tutorials/map/)
- [SensorUp SensorThings Tutorials](https://developers.sensorup.com/tutorials/)
- [SensorThingsAPI Locations on a map](https://github.com/tum-gis/FROST-on-a-map): Basic examples for bringing SensorThingsAPI Locations and HistoricalLocations to web maps as markers or trajectories.
- [NMWDI SensorThings API](https://crceanalytics.com/2022/07/07/nmwdi-sensorthings-api/)

## Presentations

- [OGC SensorThings API IoT Sensors for the Energy Domain](https://inspire.ec.europa.eu/sites/default/files/presentations/1600_ogc_sensorthings_api_and_energy_-_final.pdf)

## Videos

## Related Standards

- [Sensor Measurement Lists(SenML)](https://tools.ietf.org/html/rfc8428)

## Publications

1. [Amazon IoT and the candidate OGC SensorThings API Standard](https://www.ogc.org/blog/2315)
2. [Implementation and Evaluation of Four Interoperable Open Standards for the Internet of Things](https://www.mdpi.com/1424-8220/15/9/24343#/)
3. [An Environmental Sensor Data Suite Using the OGC SensorThings API](https://link.springer.com/chapter/10.1007/978-3-030-39815-6_22)
4. [Design and Development of an Integrated Internet of Audio and Video Sensors for COVID-19 Coughing and Sneezing Recognition](https://ieeexplore.ieee.org/abstract/document/9623141?casa_token=DdjcBl8uvxMAAAAA:fZdmWxdPp2NUSoBfu3sA2r-N6SkAkfA6phSMRunCR3Tm75OuipDHznkC87LGRqHwm_9e3EtgSw)
5. [Integration Of Heterogeneous Coronavirus Disease COVID-19 Data Sources Using OGC SensorThings API](https://www.proquest.com/openview/3a89f290aa4e754ce27f3215573add8f/1?pq-origsite=gscholar&cbl=2037681)
6. [An Automatic Embedded Device Registration Procedure Based on the OGC SensorThings API](https://scholar.google.com/scholar_url?url=https://www.mdpi.com/1424-8220/19/3/495/pdf&hl=en&oi=gsb-gga&ct=res&d=11656171690071367110&scisig=AAGBfm3mFAyEBx585JYi26bjBqji2hdlbw)
7. [The Integration of OGC SensorThings API and OGC CityGML via Sematic Web Technology](https://link.springer.com/chapter/10.1007/978-3-030-60952-8_6)
8. [A Comparative Study in the Standardization of IoT Devices Using Geospatial Web Standards](https://ieeexplore.ieee.org/abstract/document/9224992?casa_token=wET_iQDqU4YAAAAA:EyTm0T1jKbibaeLSaoEV-S2zNWj-g918Dqb89lz_HvhqkjNM13PlVgNMBSdZu_h57t6ZWRXwhw)
9. [Design and implement an interoperable Internet of Things application based on an extended OGC sensorthings API Standard](https://pdfs.semanticscholar.org/11e0/9ea6c194f61b7af59b5070911a6d6e68d639.pdf)
10. [OGC SensorThings API: Communicating "Where" in the Web of Things](https://iab.org/wp-content/IAB-uploads/2016/03/IAB_WhitePaper_OpenGeospatialConsortium.pdf)
11. [Mapping the OGC SensorThings API onto the OpenIoT Middleware](https://www.researchgate.net/publication/284995256_Mapping_the_OGC_SensorThings_API_onto_the_OpenIoT_Middleware)
12. [An Ontology Integrating the Open Standards of City Models and Internet of Things for Smart-city Applications](https://ieeexplore.ieee.org/abstract/document/9784912/)
13. [Storing and Visualising Dynamic Data in the Context of Energy Analysis in the Smart Cities](https://link.springer.com/chapter/10.1007/978-3-030-92096-8_16)
14. [OGC SensorThings API and FROST Server](https://www.geonovum.nl/uploads/documents/SensorThingsAPI%2BFROST_v01.pdf)
15. [Extending INSPIRE to the Internet of Things Through SensorThings API](https://www.mdpi.com/2076-3263/8/6/221#/)
16. [Thing Directory: simple and lightweight registry of IoT Device metadata](https://joss.theoj.org/papers/10.21105/joss.03075.pdf)
17. [Design and implement an interoperable Internet of Things application based on an extended OGC sensorthings API Standard](https://pdfs.semanticscholar.org/11e0/9ea6c194f61b7af59b5070911a6d6e68d639.pdf)
18. [An Open Internet of Things Architecture Integrating oneM2M and OGC SensorThings API Standards](http://ir.lib.ncu.edu.tw:88/thesis/view_etd.asp?URN=106322088&fileName=GC106322088.pdf)
19. [Using SensorThings API to enable a multi-platform IoT environment](https://scholar.google.com/scholar_url?url=https://repositorio-aberto.up.pt/bitstream/10216/114108/2/277716.pdf&hl=en&oi=gsb-ggp&ct=res&d=2293627466688698957&scisig=AAGBfm2V0QZnAlj-z_y8nHEkGuY-TamTDw)
20. [An Interoperable Architecture for the Internet of COVID-19 Things (IoCT) Using Open Geospatial Standards-Case Study Workplace Reopening](https://pubmed.ncbi.nlm.nih.gov/33374208/#/)
21. [SEnviro: a sensorized platform proposal using open hardware and open standards](https://www.mdpi.com/1424-8220/15/3/5555)
22. [Deployment of an open sensorized platform in a smart city context](https://www.sciencedirect.com/science/article/pii/S0167739X16305519?casa_token=jNs7PCg1Y0AAAAAA:JaH2l1--QeKz2t112ovx4LoelhOM2rNiOiRu9_cUR9mZH9jL2WUmZ28GsXaQE7zIvXvTadAPZg)
23. [Development of a Novel Approach to Search Resources in IoT](https://pdfs.semanticscholar.org/0f7d/468fba903a13d47f9d77167672e96a516203.pdf#/)
24. [Management of Sensor Data with Open Standards](https://www.researchgate.net/profile/Philipp-Hertweck/publication/334203915_Management_of_Sensor_Data_with_Open_Standards/links/5d4aa7fe4585153e59415929/Management-of-Sensor-Data-with-Open-Standards.pdf)
25. [A web service protocol realizing interoperable internet of things tasking capability](https://www.mdpi.com/1424-8220/16/9/1395)
26. [Towards Establishing Cross-Platform Interoperability for Sensors in Smart Cities](https://www.mdpi.com/1424-8220/19/3/562)
27. [OGC SensorThings API: Communicating "Where" in the Web of Things](https://iab.org/wp-content/IAB-uploads/2016/03/IAB_WhitePaper_OpenGeospatialConsortium.pdf)
28. [Viability Testing of Game Engine Usage for Visualization of 3d Geospatial Data with Ogc Standards](https://ui.adsabs.harvard.edu/abs/2022ISPAnX4W2..281W/abstract)
