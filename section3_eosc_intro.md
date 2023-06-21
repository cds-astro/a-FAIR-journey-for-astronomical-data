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

A filtering by **keywords** can also be done from the url by adding the field '&fq=keywords:%22my%20keyword%22' to the url of the results. '%22' are needed before and after the keywords as they are UTF-8 encoding of the double quotes. '%20' stands for the space.

:::::::::::::::::::::::::

:::::::::::::::: solution

### By author names

A filtering by **author names** can also be done from the url, e.g.

This search will then get all the products associated with 'Gonneau A.', as illustrated in the webpage below. 
:::::::::::::::::::::::::

:::::::::::::::: solution

### By DOI

A filtering by **keywords** can also be done from the url by adding the field '&fq=keywords:%22my%20keyword%22' to the url of the results. '%22' are needed before and after the keywords as they are UTF-8 encoding of the double quotes. '%20' stands for the space.

:::::::::::::::::::::::::


##### Example

The url modified with the extra filtering is for example: 

[https://search.marketplace.eosc-portal.eu/search/all?q=Gaia%20DR3&fq=keywords:%22Astrophysics%20and%20Astronomy%22&fq=keywords:%22stellar%20astronomy%22&fq=author_names:%22Gaia%20collaboration%22&fq=doi:%2210.26093%5C%2Fcds%5C%2Fvizier.1355%22][eosc-portal-advanced-filtering].

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
## Example: try it yourself

:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: instructor

Show some good and bad examples of filenames. 

::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::


::::::::::::::::::::::::::::::::::::: challenge

## Quiz: Are these filenames correct or not?


```
[Q1] 'my_awesome_file.fit'
[Q2] 'TABLE998.dat'
[Q3] 'myfile.jpg'
[Q4] 'table.dat'
[Q5] 'table&data.dat'
```

:::::::::::::::::::::::: solution

## Show me the solution

```
[1] "No: too long"
[2] "No: Uppercase detected"
[3] "No: Good length, but extension not supported"
[4] "Yes: correct"
[5] "No: & character not supported"
```
:::::::::::::::::::::::::::::::::
::::::::::::::::::::::::::::::::::::::::::::::::



<!--  ----------------------------------------- -->
<!--            Summary                         -->
<!--  ----------------------------------------- -->

## Summary

<!--
::::::::::::::::::::::::::::::::::::: keypoints
::::::::::::::::::::::::::::::::::::::::::::::::
-->



<!--  ----------------------------------------- -->
<!--            End	                        -->
<!--  ----------------------------------------- -->
## End!

This concludes this training on how to make your published astronomical data (table, images, spectra, …) FAIR and openly accessible to the community, and discoverable in Virtual Observatory tools such as EOSC.

