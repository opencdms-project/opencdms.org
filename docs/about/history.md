The concept for OpenCDMS arose during work on the [Climate Data Management System Specifications][1] in 2014 and was formally proposed by the [Expert Team for Climate Data Management Systems][2] (ET-CDMS) the following year.

!!! info "ET-CDMS Policy Statement"
    ET-CDMS notes that:

    - Currently, significant investment is needed to maintain a multitude of CDMS worldwide to generate data for national, regional and global analyses
    - These CDMS are not compliant with the new WMO-No.1131, Climate Data Management Systems Specifications
    - Significant investment will be required to conform to the requirements of WMO-No. 1131
    - It will be very expensive and wasteful of resources to develop the same functionality in many CDMS
    - There are several open source CDMS used by WMO Members
    - There is considerable potential to address this situation by rationalising these open source CDMS

    Therefore ET-CDMS proposes that:
    
    - Open source CDMS should converge on one Reference Open Source CDMS, namely OpenCDMS
    - Investment is required to make this happen


The OpenCDMS project was [adopted as an official project][3] of the OpenWIS Association AISBL in May 2020.

The project originally encompassed two competing and conflicting approaches (previously referred to as “top-down” and “bottom-up”). The top-down approach aimed to begin by agreeing the necessary additional standards and design for a next-generation CDMS, with the system then being implemented as a new solution built on an entirely blank canvas. 

The [bottom-up approach][4] aimed to begin with existing software and iteratively improve existing solutions to reach essentially the same outcome.

##### Reboot

By late 2022, significant progress had been made on the [WMO Climate Data Model][5] (CDM) standard. The OpenCDMS Project Technical Team took the decision to dramatically simplify the architecture of the project by adopting the CDM at the centre of the development. 

Earlier work, undertaken in OpenCDMS, creating web APIs specifically for Climsoft and MCH are now being maintained within those projects (see [December 2022 status report][6]). The original work on a complex web application, that would have supported multiple APIs, has moved into the [Climsoft project][7] and is being refactored for use in Climsoft.

These changes have allowed the OpenCDMS project to focus on becoming a Reference Implementation for the Climate Data Model standard. OpenCDMS will now achieving compatibility with other systems through interoperability with the CDM.

[1]: https://library.wmo.int/index.php?lvl=notice_display&id=16300
[2]: https://community.wmo.int/en/open-cdms-strategy
[3]: http://openwis.github.io/openwis-documentation/minutes/steering/2020-05-26and28-OpenWIS-Steering-Committee-2020-May.html
[4]: https://github.com/opencdms/opencdms-project/wiki/Workshop-Reading-May-2019
[5]: https://github.com/wmo-im/tt-cdm/blob/main/README.md
[6]: https://openclimate.net/opencdms-status-report-and-stakeholder-update-3043287a4353
[7]: https://github.com/climsoft/climsoft-app/