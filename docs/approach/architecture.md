# Architecture

<!-- CRITICAL: TODO: Add architecture diagram: Figure 3 shows the OpenCDMS technical architecture at the end of 2020 -->

The system can be viewed as following a three-tier architecture with data, application and presentation layers. However, with the main OpenCDMS core at the centre, APIs present between layers and the separation of reusable processes on the right-hand side, the approach can also be viewed as a hexagonal architecture.

The architecture follows the [principle aims](/approach/principle-aims) of the project:

1. Improve interoperability among existing CDMSs

    With many CDMSs in use around the world, currently a lot of effort is spent duplicating similar capabilities in multiple systems. The OpenCDMS Data API is intended to allow interoperability among supported systems. This will allow processes to work with multiple supported databases/CDMSs.

2. Create a Reference Implementation for a fully-compliant next-generation CDMS (with guidance from expert teams and a broad range of implementers)

    OpenCDMS does not aim to force changes on existing CDMS systems. However, one essential outcome for the project is to ensure that users have access to a CDMS that has full support for the [WMO CDMS Specifications][1] and follows best practices as they emerge from expert teams. Therefore, in addition to supporting multiple existing systems, OpenCDMS aims to also be the Reference Implementation for emerging standards and best practice.

3. Work to support, and collaborate with, existing projects with the intention of ensuring CDMS users continue to benefit from existing support structures, software and services

    OpenCDMS does not aim to replace existing CDMSs. Rather, the project aims to support, and collaborate with, existing projects to ensure that users have access to the best possible solutions that meet their specific requirements.


![OpenCDMS Architecture](/assets/images/architecture-diagram.png "OpenCDMS Architecture")

## Data Layer

<!-- TODO: The illustration of supported CDMS databases shows the focus systems at the end of 2020. However, the relationship between the OpenCDMS project and each of the projects shown has not yet been formally established. The software does not yet have support for these systems. -->

CLIDATA, CliDE, Climsoft and MCH are all essential CDMS solutions that are used extensively in developing countries. It is essential for the OpenCDMS project to support these projects and their users where possible.

MIDAS and OSCAR have been included because they bring additional capabilities and considerations for the OpenCDMS project. MIDAS is a custom CDMS developed and used by the UK Met Office. The system is of particular interest to OpenCDMS because extensive datasets, with rich and complete metadata, are available as open data.

The OSCAR/Surface system is the WMO’s official repository of WIGOS metadata for all surface-based observing stations and platforms. Ensuring full support of the WIGOS metadata standard will help with the creation of the future Reference Implementation.

It is important to note that all of the business logic required to work with each of the supported CDMSs will be implemented in adapters for the Data API. This is necessary to ensure the integrity of each system is protected. It is anticipate that OpenCDMS may only implement partial, or read-only, access to some of the supported systems.

<!-- TODO: Figure 4 illustrates the process of achieving interoperability among supported systems and also gives a feeling for the magnitude and complexity of the task. For example, the definition and use of “Station Name” varies between solutions and a formal definition of “station/platform name” existing in the WIGOS metadata standard. -->

## Application Layer

In addition to new code that is unique to OpenCDMS, the architecture also supports and encourages the reuse of products and services from existing systems through the Process API <!-- TODO: (see Glossary on page 24 for the definition of “process”)-->. The intention is that existing processes can be used without modification. The OpenCDMS process library creates a wrapper around supported processes to enable them to interact with all CDMSs that are supported through the Data API. In addition, OpenCDMS also maintains automated tests to ensure that each reused process that operates as a “black-box” is working as expected.

## Presentation Layer

All capabilities in the presentation layer will operate through the supported APIs.

The previously discussed Process and Data APIs are being implemented in the Python programming language. Although it is not expected that the average CDMS user would make direct use of these interfaces, they are available for advanced users and are useful for activities like bespoke data analysis. In addition, OpenCDMS will support multiple Web APIs. In the short-term, the project will develop, or adopt, a Web API that is intended simply for use by the OpenCDMS user interface. However, in the future the intention is to also support other API standards including the Open Geospatial Consortium Environmental Data Retrieval API (OGC API – EDR) and also a CDMS Reference API Standard if this is created alongside the CDMS Reference Implementation data model.

[1]: https://library.wmo.int/index.php?lvl=notice_display&id=16300
