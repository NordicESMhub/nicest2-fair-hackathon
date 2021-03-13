+++
title = "Day 1 HackMD"
template = "content.html"
+++

### Questions: Introduction to Open Science and FAIR data

- A reflection I had is the distinction between repeating an experiment and coming up with the same *results* versus coming to the same *conclusions*. Are these two different questions? I'm thinking about the difficulty in reproducing results in chaotic systems (like GCMs) — the results should of course converge to the same outcome
    - Exactly 👍
    - More at [https://the-turing-way.netlify.app/reproducible-research/overview/overview-definitions.html](https://the-turing-way.netlify.app/reproducible-research/overview/overview-definitions.html)

### Data management planning, data life cycle - perspective of a data manager

- This was a creative idea to start discussing how to make data more FAIR [https://www.researchdata.uni-jena.de/en/news/\_fairest+dataset_+wettbewerb](https://www.researchdata.uni-jena.de/en/news/\_fairest+dataset_+wettbewerb)
- Maybe one more idea here, that related identifiers are very important. To link your paper, code, data…
    - Yes, I think it is very important! Not always easy to do in practice.
    - Absolutely crucial!
- Aren't contact points (names) in metadata GDPR problematic?
    - I honestly don't know! The main issue is that usually we may not be aware that names are added
    - Ideally, these contacts would have to explicitly agree. We're trying to do that at least when listing contributors on a GitHub project. But completely hopeless when submitting some abstracts on EasyChair/_etc._ and asked for email addresses of all co-authors🤦🏽‍♀️

- What does "enable machine access" mean in practice?
    - for instance: information filled in DMP could be used to allocate storage (and/or computing resources?)
        - what has that got to do with me (who produced the data)? how can I have any impact on machines to find/use my data? which languages do machines speak?
        - True, well partially. If you want to apply for storage for your data then at the moment you need to fill in an application form. If the DMP were able to be read by other services then you could imagine that you fill into the DMP that you want X amount of storage at location Y. That could be picked up by the storage reservation service without you having to fill in more forms. 
- Questions to researchers: what would be useful to have in DMP?
    - Perhaps it's useful to ask: What do you wish was in the DMP of projects whose data you have used?+1
        - Where to start: I usually get a bulk of data but never know which one I should look at first.
        - This is very useful. So, are you saying that the data needs some docs on the order in which to read the data? This would come under the documentation part of the DMP. Very useful. It would be interesting to hear more things.
	- Maybe a workflow would do that (according the inputs are well defined and the workflow is not meant to describe steps only)?


### Climate researchers perspective

- Reproducibility for climate models: usually not possible and is it important?
    - I’d just like to add that bit-reproducibility is most likely going to be even  less likely to be achievable in the future, considering for example the move towards heterogenous computing with accelerators and GPUs using single precision. Therefore I guess my question is: Is the "R" in FAIR practically unreachable for climate modelling? Is this a problem?
    - Bit-reproducibility is not really needed, but if the differences can be verified to be within a certain error threshold, it would still be very useful. If reproduced data are wildly different from the original, one should question the accuracy of the original data as well, even if they were created in a different environment.

- For example, is it enough that statistics and conclusions are reproducible, but not the actual data?
    - It is probably linked to the conclusions: if they are reproducible then it may be sufficient (in climate, we are not interested in a "fully" reproducible state)

- Speaking for my example model NorESM and probably for any other large infrastructure ESM: I would argue that without access to the specific HPC architecture that my experiments are run on, it would be near impossible for anyone to even start thinking about trying to reproduce the experiments. This is not an argument against trying to produce FAIR data/code/work flow but puts questions about bit-wise reproducibility into perspective. 


- One can try one of the scientific research data hosts e.g. [https://researchdata.4tu.nl/en/about/organisation/](https://researchdata.4tu.nl/en/about/organisation/), still one has to pay for it.

    - Is this data repository used for depositing climate data?


- I’d just like to add that bit-reproducibility is most likely going to be even less likely to be achievable in the future, considering for example the move towards heterogenous computing with accelerators and GPUs using single precision. Is this a problem? For example, is it enough that statistics and conclusions are reproducible, but not the actual data?

    - Thanks a million for the point, important! Bit-reproducibility is not what's required by "reproducible science" in general.
    - Bit-reproducibility is not really needed, but if the differences can be verified to be within a certain error threshold, it would still be very useful. If reproduced data are wildly different from the original, one should question the accuracy of the original data as well, even if they were created in a different environments.
        - One issue with this is that climate simulations can be long. Historical simulations (that at least can be verified against observations) can be ~200 yrs, decadal predictions ~20 yrs, scenarios ~100 yrs into the future. Other types like spin-ups can be even several thousand years long. The fact that there individual accuracy is indeed in question is part of the reason for having ensembles and keeping a veritable zoo of models around.

- A climate researcher might know a lot of theory about FAIR data, but at the same time have no idea what to do with their own data, where to start, how to apply the "FAIR theory"

    - In CMIP, there is a lot of the data management defined and common practices are followed at all levels of the data/metadata publishing process. But:
         - What about non-CMIP data?
         - Could CMIP conventions not necessarily specific to CMIP (_e.g._ naming variables and units) be made into general conventions?
    - I think [CF](https://cfconventions.org) + [ACDD](https://wiki.esipfed.org/Attribute_Convention_for_Data_Discovery_1-3) +[ES-DOC](https://es-doc.org/) gets us a long way to describing research (modeling) data
    - As a bit of background information of CMIP (probably known to people here): [The CMIP6 Data Request](http://clipc-services.ceda.ac.uk/dreq/index.html) standardizes among other things [variables](http://clipc-services.ceda.ac.uk/dreq/index/var.html).

    - What about observations?
		- I guess observations have their own "standards".
    
- FAIR seems to me like an ideal. My practical approach as a researcher is to try to improve the fairness of my data/publication practice rather than being FAIR altogteher. 
    - I fully agree with you. I think that this is what we will see happening in research. I suspect that what FAIR means will change.



# Introduction to the hackathon aims, general discussion

- Do we only focus on climate data procued by climate models?
- Are we only interested by FAIR for machines or "FAIR" for researchers?
- At least, the published results in a peer-reviewed journal are reproducible. Is that something worth discussing?

# Technical material

- Cannot see the document in the home dir. in JupyterLab? I reloaded, but it did not help. 
    - It is located in ~/shared-ns1000k/dataporten-home/87e7b7d1-2d512f-2d4713-2d9c15-2d3a2d54fd9ca0
        - Awesome, I found it :+1: 

### ES-DOC: Introduction

- How granular is the search on es-doc, i.e. what is the smallest unit that a query result refers to?
    - The smallest queryable units are: project, institute, model, mip, document-type, document-version.
      Note that we do not have full semantic search, but we plan to enhance search capabilities via
      elastic search in Q4 2021.
- Is there any file-level info about data published on ESGF, that's available on ES-DOC?
    - Yes, the Further Info URL links back to relevant files available on the ESGF
      nodes via the 'Dataset Documentation' section against the item 'ESGF Search'.
      Also some documentation sections for given workflow components contain
      'Data link' information which links back to the data and often the file
      (though perhaps elsewhere to ESGF).
- Can't see NorESM?
    - Good question! It turns out that NorESM is referred to by the acronym 'NCC'
      (**N**orESM **C**limate modeling **C**onsortium consisting of CICERO) so when
      searching for NorESM related documentation look for 'NCC' instead of
      'NorESM'.
      - That does not show up in [the explorer](https://explore.es-doc.org/) 
- What is the link between ESGF and ES-DOC? One can publish data in ESGF and not add info in ES-DOC
    - In short, I think it could be summarised that ESGF manage and archive the *datasets* whereas
      ES-DOC manages and archives the *documentation*. ESGF have a ESG Publisher service which
      captures the relevant information about any CMIP6 data that is published in ESGF and passes
      it through to the ES-DOC ecosystem. If you add CMIP6 data via ESGF it will
      eventually be incorporated to the documentation available on ES-DOC (site and FUrther Info UR.
- ES-DOC on github: [https://github.com/ES-DOC](https://github.com/ES-DOC)
- cf-python package: [https://ncas-cms.github.io/cf-python/](https://ncas-cms.github.io/cf-python/)
- ES-DOC ocean description metadata for CMIP6: [https://specializations.es-doc.org/static/index.html?target=cmip6.ocean&client=esdoc-url-rewrite](https://specializations.es-doc.org/static/index.html?target=cmip6.ocean&client=esdoc-url-rewrite) 
 

### Errata

- How can you verify that the errata is genuine - I mean is not something malicious?
    - At the moment only the modellers themselves can create errata entries, so the likelyhood of that being malicious is rather low.
- Is there a link to errata from ESGF? Or as a researcher, should we always first search for errata before downloading/checking data?
    - I second this question, but also am wondering if it more useful when the data is e.g. sitting on a research group's server? Data straight from ESGF should already be the latest/most secure, right?
    - The link between the errata and esgf for the time being remains within the PID handles only. We have proposed an integration with the ESGF front-end, some sort of a binary signal in front of the data to signal the existence of errata. But for the time being it's not yet in implementation. We already have the API available so depends on ESGF devs. I think there needs to be a reflex adopted by researchers to first use the errata to check the sanity of data used. 
    - Quick follow-up, the reason why data available on ESGF not necessarily being the latest/safest is also due to the fact that an errata can be about something really trivial (e.g. metadata issue) and doesn't necessarily harm the content of the files for example, but also keeping older versions available for transparency and openess ends as well as reproducibility concerns.


### ES-DOC tooling and internals

- Is it easy to extend ES-DOC services to new projects?

### HackMD question: Expected hackathon outcomes

Are there specific, concrete outcomes that you can suggest for next weeks working groups?

- Low hanging fruit
    - Climate model output (research): esm2cmor (model specific) like tool for generating **metadata** only from research simulations (CF + ACDD? + ...) - push to a *simulation register*, research simulation metadata database. 
    -  Integrating DMP with (storage) services
- High value tasks
    - Pushing data from DMPs to workflow -> metadata generation (so people are not repeatedly inputing the same information in multiple places)
    - Reuse of ESGF for research simulations. What pieces are missing/required
       - Replacing MIP tables with ??
       - Errata
       - ES-DOC?
    - Metadata beyond model output? Metadata objects.
- Other
    - [https://c6dreq.dkrz.de/](https://c6dreq.dkrz.de/) data requeata requests -> database
    - ocean grids

### Planning for practical sessions 

Day 2 (03/16, 13:00-17:00 CET) and day 3 (03/17, 13:00-17:00 CET) are scheduled for practical work. We hope this provides an opportunity for those interested/motivated in diving deeper into some of the questions raised today in a breakout/working group setting?

Some ideas/suggestions for breakout themes (but we want to hear your ideas also!):

- **Tools**: Is it possible to identify one (or more) tools that are needed for metadata capture. If yes, outline the software specification.
- **Metadata**: What are the relevant metadata sources? (ACDD, CF, ES-DOC, …). What ,if anything is missing for describing research simulations/workflow? 
- **Workflow/DMP integration***: How in practice to integrate DMPs and researchers workflow to ensure information (metadata) is propagated. Are there things missing in DMPs that are important for Climate? How to make DMPs relevant & userful for researchers?
- **Big picture/roadmap (the ponderers club)**: Roadmap to FAIR climate data, collaborations: who can/should be involved (Nordic, international), governance ...



## Thoughts & inputs about hackathon

- Apply to climate and use knowledge from bio-informatics (inputs as an "outsider" from climate), interested in options / efforts towards motivating & lowering barrier
- interested to work on lowering the barrier for the scientists. There has been various developments in recent years in terms of data formats and tools (e.g NetCDF, CF-compilants) to make sure the climate data is standardized and well documented. Would it be possible to come up with automated FAIRness checks extending the meta data so that increasing our confidence in (re) using these datasets? 
- motivate on why we "should" share data. Regional modelling to catch up with the global. Publication of research climate data to ESGF to be considered to benefit from existing work 
- see on a practical example how to "make something FAIR" +1+1
- DMP integration with other services (for instance in Norway with Sigma2 MAS), ES-DOC. also interested in working on making data FAIR (practical example).
- identify existing project/tools to extend/reuse. [https://c6dreq.dkrz.de/](https://c6dreq.dkrz.de/), undertand what kind of grids are used (CMIP6, etc.), make a registry of the different grids (can be reused to re-grid)

ES-DOC ocean description metadata for CMIP6: [https://specializations.es-doc.org/static/index.html?target=cmip6.ocean&client=esdoc-url-rewrite](https://specializations.es-doc.org/static/index.html?target=cmip6.ocean&client=esdoc-url-rewrite)

- see what tools could be reused (in our own research group), from own data, consider using own researchers' *et al.*'s data as a practical example
- librarian, DMP (machine actionable) as a tool to evaluate FAIRness of the data. ES-DOC and Errata are interesting too.




