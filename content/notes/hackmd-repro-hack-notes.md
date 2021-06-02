+++
title = "Day3: Idealized citation working group: Reprohack analysis"
template = "content.html"
+++

#  Reprohack hackathon Report

The [NICEST2 hackathon on FAIR climate data](https://nordicesmhub.github.io/nicest2-fair-hackathon/) took place on March 11, 16 and 17, 2021 (13:00 - 17:00 CET). It had a combination of lectures/training and more practical sessions and discussions.
Reprohack was one of this practical sessions and span over the 2 hackathon days.

## What is a Reprohack?

A ReproHack - reproducibility hackathon - is an event where participants aim to reproduce scientific results detailed in published papers. 

**The aim of a ReproHack is absolutely not to undermine or discredit researchers or their work but to highlight their great effort and understand how to better support researchers towards Open Science.**


Reprohack participants choose a paper and then try to understand the paper and to reproduce its results, from published code and data. At the end of the reprohack, results are reported back to the authors.

See [https://github.com/reprohack/reprohack-hq](https://github.com/reprohack/reprohack-hq) for more information and links to past events.

## Reprohack during the NICEST2 FAIR Climate data hackathon

The emphasis was not on reproducibility but on the FAIRness of scientific publications. We will discuss further what we meant by it in a next section. 

We have chosen a scientific paper published by one of the hackathon's participant: 

**Humanitarian need drives multilateral disaster aid** by Dellmuth, Lisa M. and Bender, Frida A.-M. and Jönsson, Aiden R. and Rosvold, Elisabeth L. and von Uexkull, Nina. PNAS January 26, 2021 118 (4) e2018293118; [https://doi.org/10.1073/pnas.2018293118](https://doi.org/10.1073/pnas.2018293118).

Our objective is to analyze the current practices adopted by researchers and the inherent difficulties related to available infrastructures such as data archive providers and publishers.

## Who is Aiden Jönsson?

Aiden Jönsson is a PhD Student at the Department of Meteorology (MISU), Stockholm University (Sweden).

Aiden is currently doing work on the "albedo symmetry" problem: while the surface and clear-sky reflectivity of the Earth is asymmetric, the all-sky reflectivity is compensated by cloud contributions to give a remarkable degree of symmetry in all-sky reflectivity. Aiden wants to learn more about how dynamics and clouds work with Earth's radiative energy balance in order to understand why/how this would be. You can find some of his codes and notebooks at: codeberg.org/aidenrobert

Aiden is an early adopter of the Open Science principles and has done incredible efforts to make his research FAIR.

## :books: A day in the life of a researcher 

### :earth_africa: Navigate the materials


We opened the aforementioned paper: [https://www.pnas.org/content/118/4/e2018293118](https://www.pnas.org/content/118/4/e2018293118). 

#### PNAS journal

PNAS stands for *Proceedings of the National Academy of Sciences of the United States of America*.

![](https://i.imgur.com/nG51OOW.png)

To get some information on how the procedures to follow when submitting a paper, we clicked on the tab "Authors".

![](https://i.imgur.com/MdqZwuK.png)

PNAS highlights 4 main reasons why an author would choose PNAS:
- Comprehensive scientific coverage
- Broad scientific audience
- Rapid, high-quality peer review
- High impact

FAIR (Findable, Accessible, Interoperable and Reusable) is not mentioned on the main page of the **PNAS Author Center**. However, when willing to submit a paper, authors would read the more detailed [Information for Authors PDF](https://blog.pnas.org/iforc.pdf) where an entire section is dedicated to "*Materials and Data availability*".

Below is a summary of instructions given to authors for making materials, data, and associated protocols, including code and scripts, available to readers upon publication:

- Deposit data in community-approved public repositories (see the [DataCite Repository Finder](https://repositoryfinder.datacite.org/) to search for appropriate repositories) prior to publication and when possible follow the guidelines of the [Joint Declaration of Data Citation Principles](https://www.force11.org/datacitationprinciples). 
- Any restrictions on access to the data, or any parts of it, must be disclosed in detail at submission. 
- Research datasets should be deposited in an approved database prior to publication and cited in the references. 
- Make Algorithms and Computer Codes available e.g., through [Github](https://github.com/) or [Zenodo](https://zenodo.org/): the version of code associated with the paper must be maintained by the authors.


#### The paper itself

When working online (with the HTML version), we checked the Data availability link (as available from the paper publisher), which links in this case to a [Harvard Dataverse deployment](https://dataverse.harvard.edu/), which provides a list of 80+ datasets (they can be also seen in a folder-view using the Tree tab). The information in the metadata tabs seems rather simple and is probably not used too much. This is a very specific case, of course.



- While there is an option at the top to download the entire dataset, it does not seem to work. We obviously need to download files one by one which is very cumbersome (and we loose the directory structure). 

**Any technical problems will damage the reputation of researchers; not the repository itself**.

### :repeat: reproduce the analysis

- First read README.txt as we thought we would get some information on where to start.

- So we started from `undisasteraid_final.do` which is available online:

Obviously Stata has been used for some of the analysis: stata is not open source so it makes it difficult to reproduce/reuse the script provided.

- When getting a file, there is a URL but the filename (real filename) is in the text:

![](https://i.imgur.com/ewrGY7j.png)

So to download a file, we need to manually add the output filename:

```
wget https://dataverse.harvard.edu/api/access/datafile/4288994 -O accum_precip_calc.py
```
- Data from ERA-Interim (not ERA5 so we guess the analysis has been done a while ago). Forecast data is being used (not analysis) because some variables are not available for analysis (not mentionned).

However:
- We could not find precise information on the input datasets (only ERA-Interim can be downloaded).
- even though a lot of information is available online https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/VWQ5AY the paper and data are disconnected from each other (no cross-reference) so it is often difficult to understand how figures have been produced
- Many data are python or R programs: License is CC0 - "Public Domain Dedication" is not the best for software; for instance MIT should be preferred (we were not sure this can be changed when uploading data). See https://choosealicense.com/
- Stata software has been used for some part of the analysis. Stata is not open source so we cannot reproduce the work easily.
- From a general point of view, there is no description of the software used for the analysis. And for python and R programs, the list of necessary packages/libraries is missing (we could have one environment for each programming language)

#### conclusion of our attempt to reproduce the analysis

It is a complex analysis and even though a lot of information is given, we missed a summary on software (packages, versions) we need before starting to reproduce the analysis. At every step, we "discovered" it which slow down and can discourage potential users.

We suggest to add such information in the README.txt file.

### :recycle: reuse the materials


- Choose a license for your codes: there is no appropriate license for programs: CC0 - "Public Domain Dedication" cannot be used for software. We recommend the authors to add a specific license such as MIT license for all codes they share. 

- Make your code citable: deposit codes in version control repository (such as github) and prepare a release to deposit for instance in Zenodo. See more information [here](https://guides.github.com/activities/citable-code/).

- Add the codes/programs for all the steps from pre-processing, data retrievals to visualization: all the codes used for the analysis are present but we did not find any of the codes used for plotting (it may be in the stata files that we were not able to use as we did not have access to Stata software).

- It is a good practice to provide plotting routines used to generate the plots in the scientific paper. Make sure to save data used in these plotting routines (we should not need to redo all the analysis to be able to reproduce one plot).

### Conclusion on reusability

Compared to many existing scientific paper, a lot can be reused. However, contacting authors is probably still necessary to be able to reuse the datasets.

## Feedback 

### Feedback to the authors

We would like to thank all the authors and congratulate them for their effort to make their research FAIR. 
We have identified a few improvements that we believe could both improve the FAIRness of their research and ease their day to day work:

- The README.txt file could be a bit more detailed and in particular could contain information about software used. For instance, one of the software used is called Stata: it is a paid general-purpose statistical software package. Using paid software can reduce reproducibility and reusability. Whenever possible, try to use Open Source. A short explanation on why a software has been used would be useful too.

### Feedback to Universities, libraries and research institutes

- Put more emphasis on FAIR software and the usage of Open Source Software (R, python, etc.) should be encouraged (from bachelor level). Researchers use what they have learned during their studies and often have difficulties to learn new programming languages and tools. It is important to offer training to researchers to keep them aware of technological changes.
- Put more emphasis on scientific workflow management systems. This topic is unknown to many researchers while it could significantly improve the FAIRness of their research and more importantly, it could save them a lot of time.

### Feedback to data archive provider

[Harvard dataverse](https://dataverse.harvard.edu/) has not been very reliable during our hackathon: during the hackathon, we were no able to download all the files at a time with the **Download** button. We tried many times and different days and it always failed. In the absence of a clear error message, the problem can easily undermine the researcher's work and effort to make their research FAIR.


Choosing a research data archive is very important and below we give a few criteria to take into consideration:
- The research data archive must be reliable and fast enough.
- Data should be downloadable per file and also as .zip or .tar.gz or similar with a possibility to choose which file to add in the tarball. The directory structure should be preserved in the process.
- The search should be comprehensive (per author, keywords, etc.).
- Check the FAIR score with f-uji.net as this is often used to measure the FAIRness of research work (while it obviously gives a score that is mostly related to the data archive itself).


[Harvard dataverse](https://dataverse.harvard.edu/) fulfills many of these criteria but was overall very slow and difficult to use; mostly because the **Download** button was not working as expected. A week later, we managed to download the entire dataset with no problems. 

### Feedback to publisher

- FAIRness is not the criteria highlighted by PNAS journal. Emphasis is more on the review process (fast) and impact factor.
- Information for making materials, data, and associated protocols, including code and scripts, available to readers upon publication is rather generic on the PNAS journal. Similar information is found on most journal publishers.
- The [Peer Review Process](https://www.pnas.org/authors/member-contributed-submissions) does not mention anything about the FAIRness of the paper and scientific results published. Reviewers are expected to provide comments on the paper but not specifically on the "Material and Data Availability". Incentive for providing detailed and accurate information on this section is low.
- The section "**Article usage**" at the very end of each paper only highlights the number of reads (Abstract, Full, PDF). Readers have no possibility to comment on the FAIRness. This reflects the current practices in academia, for evaluating researchers.
