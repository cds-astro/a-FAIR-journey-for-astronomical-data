---
title: "Why distribute your data through VizieR?"
teaching: 2
exercises: 0
---

:::::::::::::::::::::::::::::::::::::: questions 

- What is VizieR?
- What is a VizieR catalogue?
- How is VizieR interoperable?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Be aware of the benefits of submitting your data to VizieR

::::::::::::::::::::::::::::::::::::::::::::::::



<!--  ----------------------------------------- -->
<!--            VizieR description              -->
<!--  ----------------------------------------- -->
<!-- Source: https://vizier.cds.unistra.fr/index.gml -->
## What is VizieR?

[VizieR][vizier-home] provides the most complete library of published astronomical catalogues - tables and associated data - with verified and enriched data, accessible via multiple interfaces. Query tools allow the user to select relevant data tables and to extract and format records matching given criteria. Currently, ~ 24 000 catalogues are available (as in August 2023). 


<!-- VizieR homepage as iframe-->
<iframe src="https://vizier.cds.unistra.fr/index.gml" 
title="VizieR homepage webpage" 
style="border: 1px solid black; width: 95%; height: 1000px; 
overflow: hidden; display: block; "
allowfullscreen="" allow="autoplay" data-external="1"></iframe>

<!--
width="98%" height="500px"
transform: introduces white space !!!!!
style="border: none; width: 120%; height: 1250px; 
----
-webkit-transform: scale(0.9);
-webkit-transform-origin: 0 0;
-o-transform-origin: 0 0;
-o-transform: scale(0.9);
-moz-transform-origin: 0 0;
-moz-transform: scale(0.9);
-->
VizieR homepage webpage. Note that you can type in (it is not an image).


VizieR was initially started as a joint effort of [CDS (Centre de Données astronomiques de Strasbourg)][cds-home] and ESA-ESRIN (Information Systems Division), and is now fully managed by CDS. VizieR has been available since 1996, and was described in a paper published in 2000 (DOI: [10.1051/aas:2000169][vizier-first-publi]).


Note that VizieR does not contain all available online catalogues: some catalogues are not suitable and some less frequently used catalogues have not yet been incorporated into the VizieR database. The full list of catalogues is available from there: [Catalogue collection page][vizier-catalogue-collection].

![VizieR Catalogue collection page - example for Gaia DR3 (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_catalogue_collection_may2023.png){alt="Screenshot: VizieR Catalogue collection page, example for 'mission: gaia DR3', from May 2023"}




<!--  ----------------------------------------- -->
<!--            VizieR catalogue                -->
<!--  ----------------------------------------- -->
<!-- Source: Presentation Gilles AAS 2021 -->
## What is a VizieR catalogue?

We call a VizieR catalogue:

- A set of documented tables (including a ReadMe file)
- With an indexation by keywords, authors, date ...
- With a global indexation by position
- And citation capability (bibcode or DOI)

Optionally contains:

- Photometry assignment to populate the VizieR SED service
- FITS Spectra, images and plots
- HiPS files (Hierarchical Progressive Surveys) 


<!-- VizieR catalogue as iframe-->
<iframe src="https://cdsarc.cds.unistra.fr/viz-bin/cat/I/355#/article" 
title="VizieR catalogue ingested: example Gaia DR3 Part 1." 
style="border: 1px solid black; width: 95%; height: 1200px; 
overflow: hidden; display: block; "
allowfullscreen="" allow="autoplay" data-external="1"></iframe>
VizieR catalogue ingestion webpage: example Gaia DR3 Part 1.



<!--  ----------------------------------------- -->
<!--            VizieR and VO tools             -->
<!--  ----------------------------------------- -->
## VizieR and Virtual Observatory (VO) tools

Once a catalogue is ingested in VizieR, one can access a range of tools:

- Query the [VizieR table(s)][vizier-table-search]
- Access to the [FTP][vizier-ftp] (archived VizieR tables as described by the ReadMe)
- Query VizieR table(s) using [TAP/SQL][vizier-tap]
- Perform a fast [cross-match identification][xmatch-home] between VizieR tables or Simbad
- Load your tables in [Aladin][aladin-home]
- Plot [photometry (SED)][vizier-sed] including all VizieR 
- Query VizieR [associated data][vizier-assoc-data] (images, spectra, time series)   
- Load your data as a VO Table using [TOPCAT][topcat]
- Query all VizieR catalogues using [CDS Python package][vizier-api]
- VizieR tables with astronomical objects can be processed in [SIMBAD][simbad-home].


![VizieR catalogues accessible through many VO tools](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_tools_and_vo__logos.svg){alt="Figure: VizieR and the interoperability with other VO tools. The full list of VO tools is described just above."}
 

<!--  ----------------------------------------- -->
<!--    Why distribute your data through Vizier -->
<!--  ----------------------------------------- -->
<!-- Source: Written notes from Gilles -->
## Why distribute your data through VizieR?

In addition to the interoperability with the VO tools mentioned above, distributing your data through VizieR means **adding values** to them.

- Step in search engine:
	- VO Registries: CDS Registry, [IVOA Registry of Registries (RofR)][ivoa-registry]
	- [Eudat][eudat]
	- [Astrophysics Data System (ADS)][ads]
	- [European Open Science Cloud (EOSC) Portal][eosc-portal]
- Step in the VO: interoperability with other tools, eg.
	- [CASSIS][cassis]
	- [Splat][splat]
	- astroquery
- Added metadata:
	- UCD (VO)
	- Keywords (UAT)
	- Protocol (ADQL)
	- DOI (Citation)
	- Bibcode
	- MOC



<!--  ----------------------------------------- -->
<!--            Keypoints                       -->
<!--  ----------------------------------------- -->
<!-- Source: https://cdsarc.cds.unistra.fr/vizier.submit/publication-notes.html#section1 -->
## Summary: Benefits of using VizieR

::::::::::::::::::::::::::::::::::::: keypoints

Distribute your data in a trusted repository in accordance with Open Data principles

- **Data preservation**: The CDS has been awarded the [Core Trust Seal][cts].
- **Discovery**: Take advantage of the VizieR services allowing for the discovery, and a good data visibility
	- Dedicated **indexation**
	- Quality and a good data **description**
	- Generate **persistent identifier** (bibcode, DOI) for citation
	- Data are available through the [Virtual Observatory (VO)][ivoa-link]
	<!-- - **Large publication**: data published in the Virtual Observatory -->

::::::::::::::::::::::::::::::::::::::::::::::::




<!--  ----------------------------------------- -->
<!--            Next Chapters                   -->
<!--  ----------------------------------------- -->
## Next chapters

In the next chapters, you will learn what type of data can be submitted, how to prepare and submit them to VizieR, and finally how to search your data using the EOSC tools. 




<!--  ----------------------------------------- -->
<!-- 		Link references			-->
<!--	==> See links.md file			-->
<!--  ----------------------------------------- -->
