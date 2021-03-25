+++
title = "FAIR cookbook working group HackMD"
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

Tyge demonstrates NIRD storage/DMP. Test this information in f-uji.net. Testable by:

https://www.f-uji.net/index.php 

Enter the DOI of the dataset. 


### Propagating information from DMP to workflow

Information from DMPs should be used to populate metadata (via a cookbook recipe).


## Discussion

- How should we use FAIRness measures? They should not be used to *game* the system as this doesn't necessarily improve the usefulness/(re)usability of the data. Remember, the FAIRness measure is a combination of the FAIRness of the data itself and the repository/archive.

- Separating metadata and data. Data files should be self describing and contain rich metadata. However metadata should also be extracted into a *Data Index* or *Data Catalogue* that does not store the datasets themselves but provides information about where the datasets can be obtained from. Therefore, Data Catalogues are often used to index the content of ‘Data Repositories and Data Archives.

- For publication of workflow - what information needs to be provided regarding the model used to create simulation output? Containerization. Can be used as a way to improve repeatibility. 



# Cookbook / DMP work group, Day 3 (Wednesday)

Background: https://fairplus.github.io/the-fair-cookbook/content/home.html
  - What is a "recipe?" Could be useful to define the definition of this and "cookbook" in introduction
    - Not complete, but some answers can be found here:
https://fairplus.github.io/the-fair-cookbook/content/recipes/help/how-to-create-recipe-with-git.html

To do's:
- Create a mailing list -> meeting schedule
- FAIRs fair - review of first draft.


## Create a starting template

What platform/technology should we use for a cookbook? Jupyter book?, jupyter notebook? Github. 

- During the hackathon - use HackMD
- After hackathon, migrate to github (Hamish)
- Q. How to manage pull requests?
    - A. ??


## Basic layout (first suggestion)

1. Introduction 

    - What this cookbook is, why has it been written
        - strive for best practices
    - Basics on FAIR
    - The data lifecycle - general description
        - Research objects
    - DMPs

2. Instructions on how to contribute (to this cookbook)

(Hamish)

3. Models workflow: capturing metadata

    1. NorESM / CESM 
        - How to capture metadata within workflow (general)

        - Institutional specifics
            - Bolin Centre
                - Information for reproducing workflow
                    - R markdown (examples, templates)
                    - Jupyter notebooks (examples, templates)
                    - Workflow managers (examples, templates)
                    - Container
                    - ...
                - Findability
                    - Research/metadata object
                    - ROHub
                    - WorkflowHub
                    - ...
            - UiO
                - Information for reproducing workflow
                    - R markdown (examples, templates)
                    - Jupyter notebooks (examples, templates)
                    - Workflow managers (examples, templates)
                    - Container
                    - ...
                - Findability
                    - Research/metadata object
                    - ROHub
                    - WorkflowHub
                    - ...
            - ...

    3. RCM

        - How to capture metadata within workflow (general)
            - (Geographical) domain specifications
            - Boundary data (with identifiable version, e.g. POI)
            - Version of codebase (e.g. Github commit hash), local modifications
        - Institutional specifics
            - Bolin Centre
            - UiO
            - MET Norway
            - ...

    4. ...

4. Data analysis: Recipe for citing 
    1. Data
        1. CMIP/ESGF
        2. Observations.
        3. ...
    2. Software
    3. Reproducability
        - Tools for reproducing workflow
            - R markdown (examples, templates)
            - Jupyter notebooks (examples, templates)
            - Workflow managers (examples, templates)
            - Research Objects (examples, templates)
            - ...
        - Institution specifics
            - Bolin Centre gitlab, can create a repo of source code and publish to Bolin Centre Database: https://bolin.su.se/data/
                - If separate from data (if data is hosted elsewhere for example): https://git.bolin.su.se/

5. Testing FAIRness
    - How to test FAIRness of your research work
        - data
        - software
        - workflow
        - ...
        - 

6. License (cookbook license)
    - Types of license
        - CC BY, CC BY-NC-ND
    - Legal requirements of license (by funding, etc.)

7. Acknowledgements

## Challenges
- Searchability
- Practicality of downloading/acquiring
    - Downloading from certain databases (e.g. our own in Dataverse) can be cumbersome, as all has to be downloaded at once. Can it be separated for individual download?
- Environments, containers etc.
- What data is required to be stored? (Storing only certain variables, restart files and ICs, etc.)
- Separate/consolidated metadata








