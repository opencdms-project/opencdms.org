# Simple Web API - Working Group (SWA-WG)

**Co-ordinator: (vacant)**

## Terminate date

<del>December 2020</del> (extended)<br/>
December 2022

## Deliverables

- Document existing standards and implementations that impact on the design of the Web API (December 2020)
- Develop a complete specification for version 1.0 of the Web API (December 2022)

The original plan was to complete the specification for version 1.0 of the Web API by December 2020. However, the project has focused instead on progressing the Data and Process library APIs that are being written in the Python programming language. Work on the Python APIs will inform the Web API.

<!-- OBSOLETE: The change of focus has allowed the reassessment of the approach taken to the Web API and to place the emphasis on reusing existing implementations were possible instead of creating a new specification from scratch. This approach also gives the opportunity to forge stronger links with collaborating projects that already implement Web APIs and may help to move more rapidly towards standardisation. -->

Existing standards and implementations that impact on the design of the OpenCDMS Web API are summarised below.

## Existing Web APIs

1. CLIDATA

    CLIDATA is used extensively in developing countries and has a strong presence in both Central and West Africa and the Caribbean. During discussions with the CLIDATA team it was mentioned that CLIDATA already makes use of a Web API.

    Reuse of the CLIDATA Web API in OpenCDMS would potentially have many benefits to both projects. CLIDATA is a proven CDMS solution that is very well established. The CLIDATA Web API specification is likely to support many of the capabilities that are also required by OpenCDMS. Reuse of the existing API specification would provide a clear way in which CLIDATA could become more involved in OpenCDMS.

    CLIDATA is a proprietary (closed-source) system, so OpenCDMS users would not benefit from CLIDATA software capabilities without licencing a copy of the software. However, since OpenCDMS is being developed and released under the permissive MIT open-source licence, CLIDATA users would have access to features such as the OpenCDMS process library in addition to standard CLIDATA capabilities.

2. Bureau of Meteorology

    The Australian Bureau of Meteorology has recently invested in the redevelopment of their internal CDMS and it is believed that the new system makes use of Web API(s). Reuse of their API specification in OpenCDMS would have several benefits for the Bureau, including enabling them to become more involved in the OpenCDMS project and the Bureau would also be able to benefit from the open-source capabilities being developed.

    Adoption of the Australian API specification may also help the OpenCDMS project align more closely with the CliDE project. The CliDE team intend to add a Web API at some point in the future and it is likely that this API specification may be heavily influenced by the API(s) developed in BOM.

3. Belize SURFACE

    Other options for existing APIs also exist. One possibility is the Web API recently developed for the Belize custom CDMS. The Web API is still developmental, but adoption of this Web API for OpenCDMS would present clear opportunities for both projects and should be considered if the other options above fail. The Belize SURFACE CDMS has some implementation similarities to OpenCDMS including being developed in Python (Django) and making use of TimescaleDB (which has been proposed as an option for the implementation of the OpenCDMS Reference Implementation).

## Existing API standards

In addition to an initial “simple” web API for OpenCDMS to make use of internally, the intention is to support other existing standards.

1. OGC API – Environmental Data Retrieval Standard

    Experts from the Met Office have worked with partners in the Open Geospatial Consortium (OGC) to create the OGC API - Environmental Data Retrieval Standard (OGC API – EDR). The Met Office’s externally facing services, like ServiceHub, have been influenced by this work and may converge with the standard in the future.

    Use of OGC API – EDR within OpenCDMS would allow the OpenCDMS project to also provide feedback and potential extensions to the standard (see Future API Standards below). For example, an issue has been raised on GitHub in the OpenCDMS Data Model repository for further discussion on representing dates, including the period of observations. It was agreed that partial dates, e.g. 2020-11 to represent November 2020, were not necessary since CDMSs typically record a full date and time at either the beginning or end of the observation period along with the period’s duration. Future Web API Standards are likely to need additional capabilities like being able to filter by open and closed date intervals.

## Future API Standards

No existing APIs support all of the functionalities that will be required by the next-generation CDMS Reference Implementation. The expectation is that a CDMS API Standard can be developed that can be utilised by any CDMS, where the open-source OpenCDMS code would exist as a Reference Implementation. Potentially this standard could be used for compliance testing and certification.

The CDMS Reference Implementation is likely to build on OGC API. However, even emerging standards like the OGC API – EDR do not support all of the necessary CDMS business logic and therefore further work will be required.