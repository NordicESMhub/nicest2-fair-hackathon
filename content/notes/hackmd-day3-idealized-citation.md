+++
title = "Day3: Idealized citation breakout group"
template = "content.html"
+++

### 2. Idealized citation 

    - Decide on a paper(s) to analyze citation 
        - data   
        - software
    - Push recommendations to cookbook
    - Consider a small article for EOSC-Nordic?
    - [nature paper](https://www.nature.com/articles/s41561-020-00649-1)

CMIP6 data citation; add handles for CMIP6 (Identifier, PID) for the entire dataset (not per file as a dataset can be split per time):
- id = CMIP6.CMIP.NCAR.CESM2-FV2.historical.r1i1p1f1.Amon.tas.gn ([.v20191120], http://hdl.handle.net/hdl:21.14100/8b4957ac-0912-3664-b0c2-67a8874d8974 (no need to add version because we have the PID of the dataset)
- id = CMIP6.CMIP.NCAR.CESM2-FV2.historical.r1i1p1f1.day.tas.gn, http://hdl.handle.net/hdl:21.14100/95abfd7b-5c01-39fd-8dd4-9c155d020143
- id = CMIP6.CMIP.NCAR.CESM2-FV2.historical.r2i1p1f1.day.tas.gn, http://hdl.handle.net/hdl:21.14100/ce68c95e-d0e9-32bf-ab99-19e2596c59aa
- id = CMIP6.CMIP.NCAR.CESM2-FV2.historical.r3i1p1f1.day.tas.gn, http://hdl.handle.net/hdl:21.14100/7554abc7-6fe2-3ebb-8a42-9e0def9fe0db
- id = CMIP6.CMIP.NCAR.CESM2-FV2.historical.r2i1p1f1.Amon.tas.gn, http://hdl.handle.net/hdl:21.14100/c402c2d9-cac8-3df8-9d69-7f06327dfc00
- id = CMIP6.CMIP.NCAR.CESM2-FV2.historical.r3i1p1f1.Amon.tas.gn, http://hdl.handle.net/hdl:21.14100/a587294e-5a2b-36cf-9f64-0ed1168bb862

But we could give the PID of the entire dataset.

--> the best would be to get a PID from a downloaded dataset. (to add in the cookbook); provide a simple tool to return PID from data stored on disk.

CMIP5 REST API example: https://esgf-node.llnl.gov/esg-search/search?type=File&tracking_id=826ee5e9-3cc9-40a6-a42b-d84c6b4aad97

CMIP6 REST API example: https://esgf-node.llnl.gov/esg-search/search?type=File&tracking_id=hdl:21.14100/a97ec9f6-f29f-4c79-b809-285926068043
Resolve hdl handle: https://hdl.handle.net/

#### Data-ography section


- CMIP6: list of handles and identifier (see above)
    - DOI of the code or tool to compute anomalies (version, PID). If your own tool in github, make a release and get a DOI with zenodo.
- GISTEMP v4 : no PID so download dataset and archive it to get a PID?
    - Compute annual mean (DOI of code; in that case it may be too simple and unecessary)
- Code to make Figure 1a (this code could be added with paper or github)
    - Data use for plotting saved so it is easy to reproduce the plot


