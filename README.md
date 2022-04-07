# **Awesome OGC SensorThings API** [![Awesome](https://awesome.re/badge.svg)](https://github.com/lkcozy/awesome-sensorthings-api)

A collection of awesome things regarding OGC SensorThings API(STA) ecosystem.

## OGC SensorThings API

> A standard providing an open and unified framework to interconnect IoT sensing devices, data, and applications over the Web.
> The SensorThings API is an open standard, builds on Web protocols and the OGC Sensor Web Enablement standards, and applies an easy-to-use REST-like style.

## General Resources

- [OGC SensorThings API Page](https://www.ogc.org/standards/sensorthings)
- [Online Documentation v1.0](https://developers.sensorup.com/docs/#introduction)
- [GitHub](https://github.com/opengeospatial/sensorthings)
- [Wiki Page](https://en.wikipedia.org/wiki/SensorThings_API)

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

## Tutorials

- [SensorUp Mapping with SensorThings](https://developers.sensorup.com/tutorials/map/)
- [SensorUp SensorThings Tutorials](https://developers.sensorup.com/tutorials/)

## Presentations

- [OGC SensorThings API IoT Sensors for the Energy Domain](https://inspire.ec.europa.eu/sites/default/files/presentations/1600_ogc_sensorthings_api_and_energy_-_final.pdf)

## Videos

## Related Standards

- [Sensor Measurement Lists(SenML)](https://tools.ietf.org/html/rfc8428)

## Publications

- [Amazon IoT and the candidate OGC SensorThings API Standard](https://www.ogc.org/blog/2315)
- [Implementation and Evaluation of Four Interoperable Open Standards for the Internet of Things](https://www.mdpi.com/1424-8220/15/9/24343#/)
- [An Environmental Sensor Data Suite Using the OGC SensorThings API](https://link.springer.com/chapter/10.1007/978-3-030-39815-6_22)
- [Design and Development of an Integrated Internet of Audio and Video Sensors for COVID-19 Coughing and Sneezing Recognition](https://ieeexplore.ieee.org/abstract/document/9623141?casa_token=DdjcBl8uvxMAAAAA:fZdmWxdPp2NUSoBfu3sA2r-N6SkAkfA6phSMRunCR3Tm75OuipDHznkC87LGRqHwm_9e3EtgSw)
- [The Integration of OGC SensorThings API and OGC CityGML via Semantic Web Technology](https://books.google.ca/books?hl=en&lr=&id=H4gEEAAAQBAJ&oi=fnd&pg=PA55&ots=ai_Ledffts&sig=nTs7w4FHDrBIrCkeqiwF45n2c60&redir_esc=y#v=onepage&q&f=false)
- [An Automatic Embedded Device Registration Procedure Based on the OGC SensorThings API](https://scholar.google.com/scholar_url?url=https://www.mdpi.com/1424-8220/19/3/495/pdf&hl=en&oi=gsb-gga&ct=res&d=11656171690071367110&scisig=AAGBfm3mFAyEBx585JYi26bjBqji2hdlbw)
- [The Integration of OGC SensorThings API and OGC CityGML via Sematic Web Technology](https://link.springer.com/chapter/10.1007/978-3-030-60952-8_6)
- [A Comparative Study in the Standardization of IoT Devices Using Geospatial Web Standards](https://ieeexplore.ieee.org/abstract/document/9224992?casa_token=wET_iQDqU4YAAAAA:EyTm0T1jKbibaeLSaoEV-S2zNWj-g918Dqb89lz_HvhqkjNM13PlVgNMBSdZu_h57t6ZWRXwhw)
- [Design and implement an interoperable Internet of Things application based on an extended OGC sensorthings API Standard](https://pdfs.semanticscholar.org/11e0/9ea6c194f61b7af59b5070911a6d6e68d639.pdf)
