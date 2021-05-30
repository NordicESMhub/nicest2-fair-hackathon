+++
title = "Day2: FAIR cookbook working group HackMD"
template = "content.html"
+++

# Cookbook / DMP work group, Day 2 (Tuesday)


## FAIR cookbooks

Background: https://fairplus.github.io/the-fair-cookbook/content/home.html


### Create a starting template

What platform/technology should we use for a cookbook? Jupyter book?, jupyter notebook? Github. 

- For the use case: Understand what resources are already available. Going forward make sure we have contact with the Bolin centre database managers.



### CMORization - reengineered for research

[ACDD](https://wiki.esipfed.org/Attribute_Convention_for_Data_Discovery_1-3 ) + [CF](https://cfconventions.org/). Discussion.

Can we test an example of ACDD + CF - is that sufficient metadata for describing research output?

Q. Is ACDD exetensible? At present it seems to be more taylored to measurements rather than model data. Is there a process for adding new attributes?


### Measuring FAIRness: climate data stored on NIRD

One participant demonstrates NIRD storage/DMP. Test this information in f-uji.net. Testable by:

https://www.f-uji.net/index.php 

Enter the DOI of the dataset. 


### Propagating information from DMP to workflow

Information from DMPs should be used to populate metadata (via a cookbook recipe).


## Discussion

- How should we use FAIRness measures? They should not be used to *game* the system as this doesn't necessarily improve the usefulness/(re)usability of the data. Remember, the FAIRness measure is a combination of the FAIRness of the data itself and the repository/archive.

- Separating metadata and data. Data files should be self describing and contain rich metadata. However metadata should also be extracted into a *Data Index* or *Data Catalogue* that does not store the datasets themselves but provides information about where the datasets can be obtained from. Therefore, Data Catalogues are often used to index the content of ‘Data Repositories and Data Archives.

- For publication of workflow - what information needs to be provided regarding the model used to create simulation output? Containerization. Can be used as a way to improve repeatibility. 







