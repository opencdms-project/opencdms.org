---
hide:
  - toc
---

# OpenCDMS Overview

{% include-markdown "../unlinked-pages/banner-availability.md" %}

<!--

!!! note ""
    By 2030, we see a world where all nations, especially the most vulnerable, are more resilient to the socioeconomic consequences of extreme weather, climate, water and other environmental events; and underpin their sustainable development through the best possible services, whether over land, at sea or in the air

    -- WMO Vision ([WMO Strategic Plan 2020-2023][0])

-->

The effective management of climate, hydrological and other environmental data (referred to below as Earth system data) is critical for earth observation monitoring, analysis, modelling and prediction - at the national, regional and global levels - and is essential for the effective, timely provision of related services.

One of the most important elements in being able to manage Earth system data effectively is having an effective (Climate) Data Management System (CDMS),
where ‘<abbr title="The term “climate” is considered to capture a very broad range of environmental variables, e.g. the GCOS Essential Climate Variables (ECVs)">Climate</abbr>’ is considered to be inclusive of all Earth system data with a time-series component.

## What is OpenCDMS?

The OpenCDMS Project is a community of collaborators who are working together to address Earth system data management by implementing standards and good practices. At it's core, OpenCDMS implements the [WMO Climate Data Model][1] (CDM) standard. All products, applications and services are built on top of a single shared interface (API) that represents the CDM.

<div style="text-align:center">
    <img src="/assets/images/hexagonal-architecture.png" alt="OpenCDMS hexagonal architecture" />
</div>

In addition to our own physical implementation of the Climate Data Model, called “opencdmsdb”, OpenCDMS is also able to connect to other existing CDMS using adapters that make those systems compatible with the CDM.

For more information on working with the project see [Getting Involved][2]

<!--Members of the OpenCDMS Project are currently assisting with the development of a WMO CDMS Data Model Standard.-->


<!--

The project is focused on the development and application of recommendations, best practices and standards intended for all climate data management systems and also the support and creation of free and open source software solutions to assist with implementation.

### The OpenCDMS software

The OpenCDMS software is a product of the OpenWIS Association. The goals below are all in alignment with the associations aim to: "facilitate collaboration on the development, promotion and sharing of open source software for the exchange of global meteorological information".

#### Goal 1: Reference Implementation

At a minimum, the OpenCDMS software will be a <abbr title="A program that implements all requirements from a corresponding specification and demonstrates what should be considered the &quot;correct&quot; behavior of any other implementation of it.">Reference Implementation</abbr> for Climate Data Management Standards.

This goal is also in alignment with [WMO's Mission][0] to advance standardisation and provide close coordination 
in building highly standardised systems.

{# This activity has been started with [support from WMO](/about/funding/wmo). #}


#### Goal 2: Powered by OpenCDMS

Capacity building, in line with WMO Core Values

This activity has been started with [support from the Intra-ACP Climate Services and Related Applications (ACP Project)](/about/funding/acp-project)



#### Goal 3: OpenCDMS

(stand- alone production-ready solution)


#### Goal 4: OpenCDMS Cloud

-->


[0]: https://library.wmo.int/index.php?lvl=notice_display&id=21525%20-%20.Xlz7H5NKi70
[1]: https://github.com/wmo-im/tt-cdm/blob/main/README.md
[2]: /about/get-involved