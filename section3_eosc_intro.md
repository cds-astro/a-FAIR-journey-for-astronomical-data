---
title: "Explore EOSC"
teaching: 10
exercises: 2
---

:::::::::::::::::::::::::::::::::::::: questions 

- Why publishing in EOSC / VO?
- How do you find your data in EOSC?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Be familiar with the EOSC capabilities, in particular the Explore portal.
 
::::::::::::::::::::::::::::::::::::::::::::::::




<!--  ----------------------------------------- -->
<!--            Overview                        -->
<!--  ----------------------------------------- -->
## Overview

**Warning: Text from website // TO UPDATE**

[EOSC Future][eosc-future] is an EU-funded H2020 project that is implementing the [European Open Science Cloud (EOSC)][eosc]. EOSC will give European researchers access to a wide web of FAIR data and related services.


*Ideas:*

- Added value with EOSC
- Integration done?


<!--  ----------------------------------------- -->
<!--            EOSC Portal                  -->
<!--  ----------------------------------------- -->
## EOSC Portal

**Warning: Text from website // TO UPDATE**

The [EOSC Portal][eosc-portal] is a gateway to information and resources in EOSC, providing updates on its governance and players, the projects contributing to its realisation, funding opportunities for EOSC stakeholders, relevant European and national policies, important documents, and recent developments. The EOSC Portal Catalogue & Marketplace acts as an entry point to the multitude of services and resources for researchers.

For prospective users of the services, the Portal provides training materials and tutorials on how to use its features. The Portal also offers information for potential service providers on how to onboard their services to the EOSC Portal Catalogue & Marketplace. 




![EOSC Portal homepage (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/eosc_portal_june23/eosc_portal__main_page.png){alt="Screenshot: EOSC Portal homepage, from June 2023"}



<!--  ----------------------------------------- -->
<!--            Case study 	                -->
<!--  ----------------------------------------- -->
## Case Study: Gaia DR3

In the following, we will show how to find your data in EOSC, using Gaia DR3 (Vizier DOI: [10.26093/cds/vizier.1355][vizier-gaia-dr3]) as an example.
 

### Step 1: Search 

The first step is to type the name of your catalogue, dataset, paper, DOI in the Search bar on [EOSC portal][eosc-portal], as illustrated in the figure below.

![Searching for 'Gaia DR3' on EOSC Portal -- search from homepage (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/eosc_portal_june23/case_study__gaia_dr3__step1_search.png){alt="Screenshot: EOSC Portal search for 'Gaia DR3' using homepage, from June 2023"}


You can also [browse directly the Marketplace][eosc-portal-marketplace], from the same website. You will get the same results in the end.


![Searching for 'Gaia DR3' on EOSC Portal -- Browse Marketplace tab (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/eosc_portal_june23/case_study__gaia_dr3__step1_search_browse_marketplace.png){alt="Screenshot: EOSC Portal search for 'Gaia DR3' using 'Browse Marketplace' page, from June 2023"}


---

---

### Step 2: Scan list of records

A full list of search results appear ([link to all results][eosc-portal-search-gaiadr3]), as illustrated in the figure below.
You can filter the results using the 'Filters' options on the left, or also by type of data at the top (eg. Catalogs, Publications, Data, Software ...).

In our example (Gaia DR3), we can see that the search is done on multiple fields: Title, Author names, abstract.

![Searching for 'Gaia DR3' on EOSC Portal -- all records (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/eosc_portal_june23/case_study__gaia_dr3__step2_all_records.png){alt="Screenshot: EOSC Portal search for 'Gaia DR3' -- scanning through all the records, from June 2023"}


---

<!-- --------------------- -->
### Advanced usage: filtering from the url


::::::::::::::::::::::::::::::::::::::: discussion

### Details

In addition to the filters available on the left side of the [EOSC Marketplace results page][eosc-portal-results], more advanced filetring can be done directly from the url.

:::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::: solution

### By keywords

A filtering by **keywords** can be done from the url by adding the field '&fq=keywords:%22my%20astro%20keyword%22' to the url of the results. 

'%22' are needed before and after the keywords as they are UTF-8 encoding of the double quotes. 
'%20' stands for the space.
'my astro keyword' is a placeholder for your desired keyword.

For example to filter the results using the keywords 'Astrophyiscs and Astronomy' and 'stellar astronomy', one can do: 
&fq=keywords:%22Astrophysics%20and%20Astronomy%22
&fq=keywords:%22stellar%20astronomy%22

:::::::::::::::::::::::::

:::::::::::::::: solution

### By author names

A filtering by **author names** can also be done from the url by adding the field 
'&fq=author_names:%22my%20favourite%20author%22'
to the url of the results. 

'%22' are needed before and after the keywords as they are UTF-8 encoding of the double quotes. 
'%20' stands for the space.
'my favourite author' is a placeholder for the author names.

For example to filter the results to see only the ones from the 'Gaia collaboration', one can do:
&fq=author_names:%22Gaia%20collaboration%22

:::::::::::::::::::::::::

:::::::::::::::: solution

### By DOI

Filtering by **DOI** can also be done from the url by adding the field 
'&fq=doi:%22mydoi%5C%2Fnumber%22'
to the url of the results. 

'%22' are needed before and after the keywords as they are UTF-8 encoding of the double quotes. 
'%5C%2F' stands for the slash.
'mydoi/number' is a placeholder for the DOI.

For example to filter the results to see only the DOI of Gaia DR3, one can add: 
&fq=doi:%2210.26093%5C%2Fcds%5C%2Fvizier.1355%22

:::::::::::::::::::::::::


##### Example

An example of [modified url][eosc-portal-advanced-filtering] with the extra filtering is given below: 

```
https://search.marketplace.eosc-portal.eu/search/all?q=Gaia%20DR3
&fq=keywords:%22Astrophysics%20and%20Astronomy%22
&fq=keywords:%22stellar%20astronomy%22
&fq=author_names:%22Gaia%20collaboration%22
&fq=doi:%2210.26093%5C%2Fcds%5C%2Fvizier.1355%22
```

The resulting webpage is displayed below:

<!-- Explore Portal records filtered by url as iframe-->
<iframe src="https://search.marketplace.eosc-portal.eu/search/all?q=Gaia%20DR3&fq=keywords:%22Astrophysics%20and%20Astronomy%22&fq=keywords:%22stellar%20astronomy%22&fq=author_names:%22Gaia%20collaboration%22&fq=doi:%2210.26093%5C%2Fcds%5C%2Fvizier.1355%22"
title="Explore Portal search filtering by keywords, author names and DOI (from the url)"
style="border: none; width: 98%; height: 800px; 
overflow: hidden; display: block; "
allowfullscreen="" allow="autoplay" data-external="1"></iframe>

Explore Portal search webpage: filtering by keywords, author names and DOI (from the url).



---

---

### Step 3: Select an entry

Once you found the relevant entry, you can click on it ([link to selected result][eosc-portal-result-gaiadr3]) and see many informations: Title, DOI, Date of publication, Publisher, Abstract, Relevant subjects (keywords), as illustrated in the figure below.

In this example, you can access to the resource by either clicking on the [DOI link][vizier-gaia-dr3], or on the 'Download from' on the right side of the EOSC page, and then select one of the two data sources available: [B2FIND][eosc-portal-result-gaiadr3-b2find] or [Strasbourg Astronomical Data Center][eosc-portal-result-gaiadr3-stras-datacenter].


![Searching for 'Gaia DR3' on EOSC Portal -- result (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/eosc_portal_june23/case_study__gaia_dr3__step3_result.png){alt="Screenshot: EOSC Portal search for 'Gaia DR3', from June 2023"}





<!--  ----------------------------------------- -->
<!--            Example				-->
<!--  ----------------------------------------- -->
## Examples: try it yourself

:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: instructor

Browse through EOSC Portal to find some datasets and publications, and answer the following questions.

::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::


::::::::::::::::::::::::::::::::::::: challenge

## Can you answer the following questions?


```
Q1) What is the publication date for 'Brightest cluster galaxies in Abell clusters'?
Q2) Which CDS service is listed in the 'Services' type of results?
Q3) Can you list some 'cds-astro' Softwares available?
Q4) If you published a paper or a dataset, type your name in the Search bar. What do you get as an output?
```

Hint: Browse through [EOSC Portal][eosc-portal] to answer the previous questions.

:::::::::::::::::::::::: solution

## Show me the solution

R1) This paper was published on [01 Jan 2017][eosc-question1-abell].

R2) [SIMBAD][eosc-question2-service] is the service accessible through the EOSC website.

R3) Examples of [softwares available][eosc-question3-software]: cds-astro/tutorials: v1.0.0, cds-astro/aladin-lite: Aladin Lite v3.1.1, cds-astro/cds-moc-rust: Release v0.5.2 ...
 

:::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::



<!--  ----------------------------------------- -->
<!--            Summary                         -->
<!--  ----------------------------------------- -->

## Summary

::::::::::::::::::::::::::::::::::::: keypoints

- EOSC will give European researchers access to a wide web of FAIR data and related services. 
- EOSC Portal Catalogue & Marketplace acts as an entry point to a multitude of services and resources for researchers, such as:
	- Discover Research Outputs (datasets, scientific publications, softwares)
	- Access Training Materials (lessons, courses, videos)
- The catalogues ingested in VizieR are findable and accessible in EOSC.
- Interdisciplinary science is facilitated using EOSC Portal, thanks to the interoperability of the data.
- EOSC promotes the reuse of the data. 

::::::::::::::::::::::::::::::::::::::::::::::::



<!--  ----------------------------------------- -->
<!--            End	                        -->
<!--  ----------------------------------------- -->
## End!

This concludes this training on how to make your published astronomical data (table, images, spectra, …) FAIR and openly accessible to the community, and discoverable in Virtual Observatory tools such as EOSC.

