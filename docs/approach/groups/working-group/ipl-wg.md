# Initial Process Library - Working Group (IPL-WG)

**Co-ordinator: Ian Edwards**

## Terminate date

<del>December 2020</del> (extended)<br/>
December 2021

## Deliverables

- Listing processes in order to improve awareness among the teams
- Agreeing a set of core processes for an OpenCDMS process catalogue
- Describing the core processes, including docstrings and parameterisation
- Identifying suitable test data for use in automated tests
- Writing automated tests to guarantee that processes are working as expected

The process library framework is in place, including methodologies to enable automated documentation generation from docstrings and an automated testing framework using the Python tox and pytest tools.

The approach taken was influenced by discussions with the developers of CliDEsc, a system that compliments CliDE CDMS by providing additional products and services. OpenCDMS has followed CliDEsc by adopting the Pandas data analysis library and the Pandas DataFrame as the primary data type for managing data within Python.

### Process Catalog

The working group successfully identified reusable processes from Climatol, R-Instat, Climsoft and MCH and documented these in the initial process library catalog<!-- TODO: Link to process catalogue / image -->. At the end of December 2020 the implementation only includes one process from Climatol and a single process from R-Instat. However, the route ahead from this point is well established.

The delay with R-Instat was in part due to a misunderstanding of the architecture of the software. It emerged during discussions that the front-end, written in Visual Basic .NET, and back-end which uses R are [very tightly coupled][1]. The working group also experienced some difficulties with sharing MCH code.

The process library provides the most compelling example of where OpenCDMS can add additional value to existing CDMSs and, for this reason, implementing additional processes will continue to be a high priority going forwards. The suggested aim in 2021 is to ensure that at least one additional process is added to the implementation each month from February onwards. The project must work hard to continue to support the involvement of R-Instat, MCH and other collaborators in the project.

The OpenCDMS process catalog is currently hidden in an Excel document on SharePoint. The contents should be moved to a more publicly accessible place and will be used to inform user stories for processes in the near future.<!-- TODO -->

### Grammar

The collection of processes that are made available through the OpenCDMS process library should not be created with *ad hoc* interfaces. Instead there should be a common structure, or grammar, that applies to all processes. The Initial Process Library Working Group (IPL-WG) is building on the ideas established by the Grammar of Graphics to construct the process library API ([Wilkinson 1999][2]).

The approach being developed for OpenCDMS builds on the Grammar of Graphics function chain <!-- TODO: (shown in Figure 7 above)--> and wraps this with the Extract, Transform, Load (ETL) design pattern<!-- TODO: (see Glossary information on design patterns)-->.

Constructed as a function chain, member functions within each class are interchangeable, however the classes must be applied in order. An overview of the OpenCDMS process grammar is presented below.

#### Extract

The extract step is concerned with the extraction of data from the CDMS using a common interface. For systems that fully implement the WMO Climate Data Management System Specifications the extraction of versioned data will be possible. That is to say, we should be able to ask for the version of the data that would have been returned if the query had been made on a specific date (data may vary depending on quality control processes).

#### Transform

The transform step in the chain corresponds closely to the original four classes in the Grammar of Graphics. This may involve reshaping the data and transforming variable (e.g. converting a date into the corresponding value for the day in year, or creating a summary statistic). The initial transform steps will often be performed once and then the resulting transformed data will be reused for multiple processes.

#### Process

The final three classes from Grammar of Graphics allow the creation of very diverse graphical outputs. It’s not clear whether the process API will expose this capability directly to users. However, we aspire to allow this level of flexibility to internal OpenCDMS processes to enable a very broad range of capabilities in addition to a taxonomy of processes.

#### Load

The final Load stage determines what happens to the generated output, this may be as simple as displaying a graph, writing an image or tabular data to a file, adding the product to a message queue to be emailed or writing quality controlled data back to the CDMS.
The OpenCDMS library should support lazy loading of data, working with a data definition without loading the data payload. It should be possible to perform operations like observations.count() without retrieving all of the data. Similarly print(observations) may only require a paginated subset to be retrieved.

### Supported libraries

In addition to R-Instat and MCH, the intention is to add support for CliDEsc processes and to also rewrite many Climsoft core processes and make these accessible via JavaScript.

[1]: https://github.com/opencdms/opencdms-project/wiki/~PTT-2020-11-18#2-overview-of-recent-work-on-r-instat-processes
[2]: https://www.springer.com/gp/book/9780387245447