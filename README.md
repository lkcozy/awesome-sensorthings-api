# Awesome OGC SensorThings API[![Awesome](https://awesome.re/badge.svg)](https://github.com/lkcozy/awesome-sensorthings-api)

A collection of awesome things regarding OGC SensorThings API(STA) ecosystem.

- [Awesome OGC SensorThings API](#awesome-ogc-sensorthings-api)
  - [OGC SensorThings API Highlight](#ogc-sensorthings-api-highlight)
    - [Entities](#entities)
    - [Example Query](#example-query)
  - [Standard Specification](#standard-specification)
  - [General Resources](#general-resources)
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

## OGC SensorThings API Highlight

> A standard providing an open and unified framework to interconnect IoT sensing devices, data, and applications over the Web.
> Builds on Web protocols and the OGC Sensor Web Enablement standards, and applies an easy-to-use REST-like style.

- For exchanging sensor data and metadata
  - Historic data & current data
  - JSON Encoded
  - RESTful
  - Adapting OASIS OData URL patterns and query options
  - Supporting OASIS MQTT messaging

### Entities

![sensing](https://developers.sensorup.com/assets/images/STA-1.0-UML.jpg)

![tasking 1.0](https://developers.sensorup.com/assets/images/SensorThingPart2UML.png)

- Sensing
  - Thing: an object of the physical world (physical things) or the information world (virtual things) that is capable of being identified and integrated into communication networks
  - Location: locates the Thing or the Things it associated with
  - HistoricalLocation: provides the current (i.e., last known) and previous locations of the Thing with their time
  - Datastream: a collection of Observations and the Observations in a Datastream measure the same ObservedProperty and are produced by the same Sensor
  - Sensor: an instrument that observes a property or phenomenon with the goal of producing an estimate of the value of the property
  - ObservedProperty: specifies the phenomenon of an Observation
  - Observation: act of measuring or otherwise determining the value of a property
  - FeatureOfInterest: an observation results in a value being assigned to a phenomenon. The phenomenon is a property of a feature, the latter being the FeatureOfInterest of the Observation.
- Tasking
  - TaskingCapability: specifies the task-able parameters of an actuator
  - Task: a piece of work to be done
  - Actuator: a type of transducer that converts a signal to some real-world action or phenomenon
- STAplus
  - Party: links a user to a Datastream, MultiDatastream, Campaign or ObservationGroup and Thing
  - License: expresses reuse conditions by linking a License to a Datastream, MultiDatastream, and / or to a ObservationGroup.
  - ObservationGroup: packages individual Observations as a bag or set either as deep copy or via linking
  - Relation: expresses relationships between Observation entities using the “-to” role type
  - Campaign: a container of Datastream, MultiDatastream and ObservationGroup entities that supports organizing a campaign or project and to provide metadata as well as legal information such as terms of use and a privacy statement, in case it is relevant.

### Example Query

[The query to fetch all data to display on a map](https://brgm.hal.science/hal-04456540/file/Integration%20of%20new%20OGC%20Standards%20e.g%20SensorThings%20API.pdf)

```sh
v1.1/Things?
    $select=id,name,description,properties&
    $top=10&
    $filter=properties/countryCode eq 'HR'&
    $expand=
      Locations($select=location),
      Datastreams(
        $select=id,name,unitOfMeasurement;
        $expand=
        ObservedProperty($select=name),
        Observations(
          $select=result,phenomenonTime;
          $orderby=phenomenonTime desc;
          $top=1)
```

[Results](<https://airquality-frost.k8s.ilt-dmz.iosb.fraunhofer.de/v1.1/Things?$select=id,name,description,properties&$top=10&$filter=properties/countryCode%20eq%20%27HR%27&$expand=Locations($select=location),Datastreams($select=id,name,unitOfMeasurement;$expand=ObservedProperty($select=name),Observations($select=result,phenomenonTime;$orderby=phenomenonTime%20desc;$top=1))>)

## Standard Specification

- [Part 1: Sensing 1.1(2021)](https://docs.ogc.org/is/18-088/18-088.html) ([PDF version](https://docs.ogc.org/is/18-088/18-088.pdf))
- [Part 1: Sensing 1.0(2016)](http://docs.opengeospatial.org/is/15-078r6/15-078r6.html): Management and reception of observations or measurements made by IoT sensors
- [Part 2: Tasking Core 1.0(2019)](http://docs.opengeospatial.org/is/17-079r1/17-079r1.html): Tell the sensor/actuator what to do
- Part 3: Rules Engine: TBD
- Part 4: Tasking Extensions: TBD
- [OGC SensorThings API Extension: STAplus 1.0](https://docs.ogc.org/is/22-022r1/22-022r1.html): standardizes citizen data and make it accessible, interoperable and reusable among different citizen observations (COs) and service. It has added these aspects: **ownership of the observations, citizen science project or campaign, link between observations-author-project**. It is a 100% backwards-compatible extension to the SensorThings data model v1.1.

## General Resources

- [OGC SensorThings API Page](https://www.ogc.org/standards/sensorthings)
- [Online Documentation v1.0](https://developers.sensorup.com/docs/#introduction)
- [GitHub](https://github.com/opengeospatial/sensorthings)
- [Wiki Page](https://en.wikipedia.org/wiki/SensorThings_API)
- [SensorUp SensorThings API Documentation](https://developers.sensorup.com/docs/#introduction)
- [SensorThings API HowTo](https://fraunhoferiosb.github.io/FROST-Server/sensorthingsapi/1_Home.html)

## Sandbox Services

- [Fraunhofer IOSB v1.1](https://ogc-demo.k8s.ilt-dmz.iosb.fraunhofer.de/v1.1/)
- [Air quality v1.1](https://airquality-frost.k8s.ilt-dmz.iosb.fraunhofer.de/v1.1)
- [SensorUp Toronto Bike v1.0](https://toronto-bike-snapshot.sensorup.com/display/v1.0)

## Tools

- [SensorUp STA Interactive SDK](https://developers.sensorup.com/InteractiveSDK/): A fun and easy way to learn how to use the OGC SensorThings API.
- [SensorUp STA Dashboard](http://dashboard-demo.sensorup.com/): STA Dashboard
- [SensorUp STA Browser](http://map-dashboard.sensorup.com/components/settings/index.html): STA Browser
- [SensorUp STA EXplorer](https://explorer.sensorup.com/?url=https://toronto-bike-snapshot.sensorup.com/v1.0):Generic visualization dashboard for SensorThings
- [SensorUp STA Share](https://share.sensorup.com/): Create and share snippets of code to showcase SensorThings
- [FROST-Server](https://github.com/FraunhoferIOSB/FROST-Server):The FRaunhofer Opensource SensorThings-Server is the first complete, open-source implementation of the OGC SensorThings API Part 1: Sensing
- [FROST-Server Fine-Grained Security with Projects](https://github.com/hylkevds/FROST-Server.Plugin.Projects/): A fine-grained security definition for FROST-Server, based on Projects.
- [FROST-GeoJSON-Importer](https://github.com/hylkevds/FROST-GeoJsonImporter): A tool for importing GeoJSON FeatureCollections as Locations & Things into a SensorThings API compatible service.
- [Frost-Client](https://github.com/FraunhoferIOSB/FROST-Client): a Java-based client library for the SensorThingsAPI and aims to simplify development of SensorThings enabled client applications.
- [SensorThings API Python Client](https://pypi.org/project/frost-sta-client/#/): a client library to facilitate interaction with a FROST SensorThingsAPI Server
- [Geodan SensorThings .NET SDK](https://github.com/gost/sensorthings-net-sdk) : makes it easy to add OGC SensorThings support to your .NET application.
- [stapy](https://github.com/zMoooooritz/stapy): An easy to use SensorThings API Client written in Python
- [sensor-things-server](https://github.com/PAR-Government/sensor-things-server): Implementation of OGC SensorThings server in .NET that is suitable for being embedded into Xamarin
- 🐳 [sensorcamp-munich](https://github.com/lrswss/sensorcamp-munich): Docker stack to setup a LoRaWAN infrastructure including a FROST-Server on a Raspberry Pi
- [Grafana OGC SensorThings Plugin](https://grafana.com/grafana/plugins/linksmart-sensorthings-datasource/): This plugin enables the visualization of sensor and location data from an OGC SensorThings server on Grafana.
- [STAM (SensorThings API Map)](https://github.com/DataCoveEU/STAM): The JS library for showing the Things/Features of interest of a SensorThings server on a Leaflet/OpenLayers map.
- [sensorweb-server-sta](https://github.com/52North/sensorweb-server-sta/tree/sta-dao-cloudnative)This is an implementation of the `OGC SensorThings API Part I: Sensing`.

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
- [SensorThings API - Quick Start](https://labs.waterdata.usgs.gov/docs/sensorthings/about-sensor-things-pbs-api/index.html)
- [SensorThingsAPI Locations on a map](https://github.com/tum-gis/FROST-on-a-map): Basic examples for bringing SensorThingsAPI Locations and HistoricalLocations to web maps as markers or trajectories.
- [NMWDI SensorThings API](https://crceanalytics.com/2022/07/07/nmwdi-sensorthings-api/)
- [Cos4Cloud STAplus Viewer App](https://cos4cloud.demo.secure-dimensions.de/combi-viewer-app/)

## Presentations

- [Integrating new OGC Standards - SensorThings API and WaterML2.0 - Water Quality Interoperability experiment](https://brgm.hal.science/hal-04456540/file/Integration%20of%20new%20OGC%20Standards%20e.g%20SensorThings%20API.pdf)
- [OGC SensorThings API IoT Sensors for the Energy Domain](https://inspire.ec.europa.eu/sites/default/files/presentations/1600_ogc_sensorthings_api_and_energy_-_final.pdf)
- [Processes and Tools for enabling Interoperability between Citizen Science and Expert Biodiversity Data in Agriculture](https://pure.iiasa.ac.at/id/eprint/18995/1/ISDEpresentation.pdf)

## Videos

## Related Standards

- [Sensor Measurement Lists(SenML)](https://tools.ietf.org/html/rfc8428)
- [STAplus: an extended data model for the SensorThings API](https://zenodo.org/record/7657751): STAplus aims to standardize citizen science data and make it accessible, interoperable and reusable among different citizen observatories (COs) and services. In particular, STAplus is an extended data model for the SensorThings API, an international Open Geospatial Consortium standard used to interconnect devices, data and applications that work on the Internet.

![](https://cos4cloud-eosc.eu/wp-content/uploads/2022/07/Captura-de-Pantalla-2022-07-15-a-las-14.42.53-1536x1085.png)

## Publications

1. [Amazon IoT and the candidate OGC SensorThings API Standard](https://www.iotone.com/guide/amazon-iot-and-the-candidate-ogc-sensorthings-api-standard/g586)
2. [OGC SensorThings API: Communicating "Where" in the Web of Things](https://www.ietf.org/slides/slides-iotsiws-ogc-sensorthings-api-communicating-where-in-the-web-of-things-00.pdf)
3. [Implementation and Evaluation of Four Interoperable Open Standards for the Internet of Things](https://www.mdpi.com/1424-8220/15/9/24343#/)
4. [An Environmental Sensor Data Suite Using the OGC SensorThings API](https://link.springer.com/chapter/10.1007/978-3-030-39815-6_22)
5. [Design and Development of an Integrated Internet of Audio and Video Sensors for COVID-19 Coughing and Sneezing Recognition](https://ieeexplore.ieee.org/abstract/document/9623141?casa_token=DdjcBl8uvxMAAAAA:fZdmWxdPp2NUSoBfu3sA2r-N6SkAkfA6phSMRunCR3Tm75OuipDHznkC87LGRqHwm_9e3EtgSw)
6. [Integration Of Heterogeneous Coronavirus Disease COVID-19 Data Sources Using OGC SensorThings API](https://www.proquest.com/openview/3a89f290aa4e754ce27f3215573add8f/1?pq-origsite=gscholar&cbl=2037681)
7. [An Automatic Embedded Device Registration Procedure Based on the OGC SensorThings API](https://scholar.google.com/scholar_url?url=https://www.mdpi.com/1424-8220/19/3/495/pdf&hl=en&oi=gsb-gga&ct=res&d=11656171690071367110&scisig=AAGBfm3mFAyEBx585JYi26bjBqji2hdlbw)
8. [The Integration of OGC SensorThings API and OGC CityGML via Sematic Web Technology](https://link.springer.com/chapter/10.1007/978-3-030-60952-8_6)
9. [A Comparative Study in the Standardization of IoT Devices Using Geospatial Web Standards](https://ieeexplore.ieee.org/abstract/document/9224992?casa_token=wET_iQDqU4YAAAAA:EyTm0T1jKbibaeLSaoEV-S2zNWj-g918Dqb89lz_HvhqkjNM13PlVgNMBSdZu_h57t6ZWRXwhw)
10. [Design and implement an interoperable Internet of Things application based on an extended OGC sensorthings API Standard](https://pdfs.semanticscholar.org/11e0/9ea6c194f61b7af59b5070911a6d6e68d639.pdf)
11. [OGC SensorThings API: Communicating "Where" in the Web of Things](https://www.ietf.org/slides/slides-iotsiws-ogc-sensorthings-api-communicating-where-in-the-web-of-things-00.pdf)
12. [Mapping the OGC SensorThings API onto the OpenIoT Middleware](https://www.researchgate.net/publication/284995256_Mapping_the_OGC_SensorThings_API_onto_the_OpenIoT_Middleware)
13. [An Ontology Integrating the Open Standards of City Models and Internet of Things for Smart-city Applications](https://ieeexplore.ieee.org/abstract/document/9784912/)
14. [Storing and Visualising Dynamic Data in the Context of Energy Analysis in the Smart Cities](https://link.springer.com/chapter/10.1007/978-3-030-92096-8_16)
15. [OGC SensorThings API and FROST Server](https://www.geonovum.nl/uploads/documents/SensorThingsAPI%2BFROST_v01.pdf)
16. [Extending INSPIRE to the Internet of Things Through SensorThings API](https://www.mdpi.com/2076-3263/8/6/221#/)
17. [Thing Directory: simple and lightweight registry of IoT Device metadata](https://joss.theoj.org/papers/10.21105/joss.03075.pdf)
18. [Design and implement an interoperable Internet of Things application based on an extended OGC sensorthings API Standard](https://pdfs.semanticscholar.org/11e0/9ea6c194f61b7af59b5070911a6d6e68d639.pdf)
19. [An Open Internet of Things Architecture Integrating oneM2M and OGC SensorThings API Standards](http://ir.lib.ncu.edu.tw:88/thesis/view_etd.asp?URN=106322088&fileName=GC106322088.pdf)
20. [Using SensorThings API to enable a multi-platform IoT environment](https://scholar.google.com/scholar_url?url=https://repositorio-aberto.up.pt/bitstream/10216/114108/2/277716.pdf&hl=en&oi=gsb-ggp&ct=res&d=2293627466688698957&scisig=AAGBfm2V0QZnAlj-z_y8nHEkGuY-TamTDw)
21. [An Interoperable Architecture for the Internet of COVID-19 Things (IoCT) Using Open Geospatial Standards-Case Study Workplace Reopening](https://pubmed.ncbi.nlm.nih.gov/33374208/#/)
22. [SEnviro: a sensorized platform proposal using open hardware and open standards](https://www.mdpi.com/1424-8220/15/3/5555)
23. [Deployment of an open sensorized platform in a smart city context](https://www.sciencedirect.com/science/article/pii/S0167739X16305519?casa_token=jNs7PCg1Y0AAAAAA:JaH2l1--QeKz2t112ovx4LoelhOM2rNiOiRu9_cUR9mZH9jL2WUmZ28GsXaQE7zIvXvTadAPZg)
24. [Development of a Novel Approach to Search Resources in IoT](https://pdfs.semanticscholar.org/0f7d/468fba903a13d47f9d77167672e96a516203.pdf)
25. [Management of Sensor Data with Open Standards](https://www.researchgate.net/profile/Philipp-Hertweck/publication/334203915_Management_of_Sensor_Data_with_Open_Standards/links/5d4aa7fe4585153e59415929/Management-of-Sensor-Data-with-Open-Standards.pdf)
26. [A web service protocol realizing interoperable internet of things tasking capability](https://www.mdpi.com/1424-8220/16/9/1395)
27. [Towards Establishing Cross-Platform Interoperability for Sensors in Smart Cities](https://www.mdpi.com/1424-8220/19/3/562)
28. [Viability Testing of Game Engine Usage for Visualization of 3d Geospatial Data with Ogc Standards](https://ui.adsabs.harvard.edu/abs/2022ISPAnX4W2..281W/abstract)
29. [The template for a Semantic SensorThings API with the GloSIS use case](https://isprs-archives.copernicus.org/articles/XLVIII-4-W12-2024/29/2024/isprs-archives-XLVIII-4-W12-2024-29-2024.pdf)
30. [Hypermedia-driven RESTful API for digital twins of the built environment](https://www.sciencedirect.com/science/article/pii/S0926580524002875)
