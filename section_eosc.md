---
title: "Journey of your data in the VO and EOSC"
teaching: 5
exercises: 1
---

:::::::::::::::::::::::::::::::::::::: questions 

- What happens to your data after their ingestion in VizieR?
- How does your published data get into EOSC?
- Why publish to EOSC / VO?
- How do you find your data in EOSC?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Understand the integration of astronomy data services in the VO and EOSC.
- Be familiar with the EOSC capabilities, in particular the Explore portal.
 
::::::::::::::::::::::::::::::::::::::::::::::::


<!-- title: "Explore EOSC"  /// Older -->
<!--  ----------------------------------------- -->
<!--            Journey of your data            -->
<!--  ----------------------------------------- -->
## From Vizier to EOSC

Once your data have been successfully ingested into VizieR, they begin their journey into the Virtual Observatory, ultimately reaching the  [European Open Science Cloud (EOSC)][eosc], as illustrated in the figure below.

![Full data journey from a publication to EOSC: last step of the journey - step integration into the IVOA, EUDAT and finally EOSC](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/lighthouse/full.svg){alt="Figure -- Summary data journey from a publication to VizieR and then EOSC: last step of the journey - step integration into the IVOA, EUDAT and finally EOSC, right after - step data published in a refereed paper, step preparation of the data, step submission of the data, steps curation and verification of the data"}

The first stop for your data after VizieR is the International Virtual Observatory Association (IVOA) registry. It gathers the data from ViZieR, and other astronomical data centers.

Then the datasets reach a broader audience when B2Find and the EOSC registries gather information (harvest) about everything emitted by the IVOA registry.



<!--  ----------------------------------------- -->
<!--            EOSC	                        -->
<!--  ----------------------------------------- -->
## The European Open Science Cloud (EOSC)

[EOSC][eosc] is the European web of FAIR data and related services for research. 
It stands for European Open Science Cloud and it aims to make research data easy to find, access, interoperate and reuse (FAIR), making trusted and sustainable research outputs available within and across scientific disciplines. 

The EOSC ambition is to federate existing data, research and e-infrastructures to make them all available to European researchers across borders and across disciplines.


<!--  ----------------------------------------- -->
<!--            EOSC Portal                  -->
<!--  ----------------------------------------- -->
## EOSC Portal

The [EOSC Portal][eosc-portal]  is one of the results of the [EOSC Future][eosc-future], European Commission funded project (2019-2023).
It provides an interface to EOSC for researchers to utilise the full spectrum of EOSC resources, which include research publications, data, software, and value-added services to support their research.

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

A filtering by **keywords** can be done from the url by adding the field *&fq=keywords:"my%20astro%20keyword"* to the url of the results. 

<!-- '%22' are needed before and after the keywords as they are UTF-8 encoding of the double quotes. -->
'%20' is the UTF-8 encoding for the space.
'my astro keyword' is a placeholder for your desired keyword.

For example to filter the results using the keywords 'Astrophyiscs and Astronomy' and 'stellar astronomy', one can do: 
&fq=keywords:"Astrophysics%20and%20Astronomy"
&fq=keywords:"stellar%20astronomy"

:::::::::::::::::::::::::

:::::::::::::::: solution

### By author names

A filtering by **author names** can also be done from the url by adding the field 
*&fq=author_names:"my%20favourite%20author"*
to the url of the results. 

<!-- '%22' are needed before and after the keywords as they are UTF-8 encoding of the double quotes. -->
'%20' is the UTF-8 encoding for the space.
'my favourite author' is a placeholder for the author names.

For example to filter the results to see only the ones from the 'Gaia collaboration', one can do:
&fq=author_names:"Gaia%20collaboration"

:::::::::::::::::::::::::

:::::::::::::::: solution

### By DOI

Filtering by **DOI** can also be done from the url by adding the field 
*&fq=doi:"mydoi%5C%2Fnumber"*
to the url of the results. 

<!-- '%22' are needed before and after the keywords as they are UTF-8 encoding of the double quotes. -->
'%5C%2F' stands for the slash.
'mydoi/number' is a placeholder for the DOI.

For example to filter the results to see only the DOI of Gaia DR3, one can add: 
&fq=doi:"10.26093%5C%2Fcds%5C%2Fvizier.1355"

:::::::::::::::::::::::::


##### Example

An example of [modified url][eosc-portal-advanced-filtering] with the extra filtering is given below: 

```
https://search.marketplace.eosc-portal.eu/search/all?q=Gaia%20DR3
&fq=keywords:"Astrophysics%20and%20Astronomy"
&fq=keywords:"stellar%20astronomy"
&fq=author_names:"Gaia%20collaboration"
&fq=doi:"10.26093%5C%2Fcds%5C%2Fvizier.1355"
```


![Searching for 'Gaia DR3' on EOSC Portal -- all records, with extra filtering (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/eosc_portal_june23/case_study__gaia_dr3__step2_all_records_advanced_filtering.png){alt="Screenshot: EOSC Portal search for 'Gaia DR3' -- scanning through all the records and filtering using the url, from June 2023"}



<!-- iframe commented on 22/06/23:  
The resulting webpage is displayed below:

//  Explore Portal records filtered by url as iframe 
<iframe src="https://search.marketplace.eosc-portal.eu/search/all?q=Gaia%20DR3&fq=keywords:%22Astrophysics%20and%20Astronomy%22&fq=keywords:%22stellar%20astronomy%22&fq=author_names:%22Gaia%20collaboration%22&fq=doi:%2210.26093%5C%2Fcds%5C%2Fvizier.1355%22"
title="Explore Portal search filtering by keywords, author names and DOI (from the url)"
style="border: none; width: 98%; height: 800px; 
overflow: hidden; display: block; "
allowfullscreen="" allow="autoplay" data-external="1"></iframe>

Explore Portal search webpage: filtering by keywords, author names and DOI (from the url).
-->


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
Q4) Advanced question: can you find the dataset associated with the word 'Astronomy'
and published by the 'National Radio Astronomy Observatory'? 
Q5) If you published a paper or a dataset, type your name in the Search bar. 
What do you get as an output?
```

Hint: Browse through [EOSC Portal][eosc-portal] to answer the previous questions.

:::::::::::::::::::::::: solution

## Show me the solution

R1) This paper was published on [01 Jan 2017][eosc-question1-abell].

R2) [SIMBAD][eosc-question2-service] is the service accessible through the EOSC website.

R3) Examples of [softwares available][eosc-question3-software]: [cds-astro/tutorials: v1.0.0][eosc-question3-tutorials], [cds-astro/aladin-lite: Aladin Lite v3.1.1][eosc-question3-alatin-lite], [cds-astro/cds-moc-rust: Release v0.5.2][eosc-question3-cds-moc-rust] ...

R4) Select first 'Astronomy' in the Search bar, and 'Data' from the scrolling menu.
Submit this search (press Enter on the keyboard) and then add '&fq=author_names:"National%20Radio%20Astronomy%20Observatory"' to the url.

The search result Data should look like: [search-result][eosc-question4-dataset]
 
:::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::::::::::::::



<!--  ----------------------------------------- -->
<!--            Summary                         -->
<!--  ----------------------------------------- -->

## Summary

::::::::::::::::::::::::::::::::::::: keypoints

- EOSC is not a new digital infrastructure.
- EOSC will support the cultural change towards Open Science and FAIR principles in the EU countries and institutions.
- Individual researchers will benefits from EOSC through their existing channels (e.g. universities, research institutes, research infrastructures, associations, science clusters, etc.) that will act as intermediaries. 

- EOSC will allow for universal access to data and a new level playing field for EU researchers.


- EOSC Portal Catalogue & Marketplace acts as an entry point to a multitude of services and resources for researchers, such as:
	- Discover Research Outputs (datasets, scientific publications, softwares)
	- Access Training Materials (lessons, courses, videos)

- The catalogues ingested in VizieR are findable and accessible in EOSC!

- Interdisciplinary science is facilitated using EOSC Portal, thanks to the interoperability of the data.
- EOSC promotes the reuse of the data. 

::::::::::::::::::::::::::::::::::::::::::::::::



<!--  ----------------------------------------- -->
<!--            End	                        -->
<!--  ----------------------------------------- -->
## End!

This concludes this training on how to make your published astronomical data (table, images, spectra, …) FAIR and openly accessible to the community, and discoverable in Virtual Observatory tools such as EOSC.



