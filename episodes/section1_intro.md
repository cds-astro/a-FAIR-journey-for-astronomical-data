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

- Describe the contents of a VizieR catalogue
- List some VO tools interoperable with VizieR catalogues
- Outline the benefits of submitting your data to VizieR

::::::::::::::::::::::::::::::::::::::::::::::::



<!--  ----------------------------------------- -->
<!--            VizieR description              -->
<!--  ----------------------------------------- -->
<!-- Source: https://vizier.cds.unistra.fr/index.gml -->
## What is VizieR?

[VizieR][vizier-home] provides the most complete library of published astronomical catalogues - tables and associated data - with verified and enriched data, accessible via multiple interfaces. Query tools allow the user to select relevant data tables and to extract and format records matching given criteria. Currently, ~ 24 000 catalogues are available (as in August 2023). 


<!-- VizieR homepage as iframe-->
Interactive window: VizieR homepage webpage. Note that you can type in (it is not an image).
<iframe src="https://vizier.cds.unistra.fr/index.gml" 
title="VizieR homepage webpage" 
style="border: 1px solid black; width: 95%; height: 1000px; 
overflow: hidden; display: block; "
allowfullscreen="" allow="autoplay" data-external="1"></iframe>


VizieR was initially started as a joint effort of [CDS (Centre de Données astronomiques de Strasbourg)][cds-home] and ESA-ESRIN (Information Systems Division), and is now fully managed by CDS. VizieR has been available since 1996, and was described in a paper published in 2000 (DOI: [10.1051/aas:2000169][vizier-first-publi]).


Note that VizieR does not contain all available online catalogues: some catalogues are not suitable and some less frequently used catalogues have not yet been incorporated into the VizieR database. The full list of catalogues is available from there: [Catalogue collection page][vizier-catalogue-collection].

![Figure: VizieR Catalogue collection page - example when selecting Gaia mission catalogues (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_catalogue_collection_july2023.png){alt="Screenshot: VizieR Catalogue collection page, example for 'mission:gaia', from July 2023"}


VizieR and more generally speaking the CDS are quite involved in the data preservation aspect,
as evidenced by the [DSA][dsa] and [CTS][cts] certifications awarded over the last years. 
More details on the topic can be found at the page below.


<!-- CDS certification CTS -->
Interactive window: CDS webpage related to the CoreTrustSeal certification.
<iframe src="https://cds.unistra.fr/CTS-CDS"
title="CDS is certified by the CoreTrustSeal"
style="border: 1px solid black; width: 95%; height: 900px; 
overflow: hidden; display: block; "
allowfullscreen="" allow="autoplay" data-external="1"></iframe>



<!--  ----------------------------------------- -->
<!--            VizieR catalogue                -->
<!--  ----------------------------------------- -->
<!-- Source: Presentation Gilles AAS 2021 -->
## What is a VizieR catalogue?

We call a VizieR catalogue:

- A set of documented tables (including a ReadMe file), linked to a published paper
- With an indexation by keywords, authors, date, UCDs ...
- With a global indexation by position whenever possible
- And citation capability (bibcode or DOI)

A catalogue can optionally contains other data types, also associated with publications.
Here is a non exhaustive list:

- Photometric information: this will populate the [VizieR SED service][vizier-sed]
- FITS Spectra, images and cubes: this will populate the [associated Saada/VizieR database][vizier-assoc-data]
<!-- - HiPS files (Hierarchical Progressive Surveys)  -->
- Time series and spectra: they will be displayed as interactive plot (see [example of interactive time serie plot][vizier-timeserie-example])
- Table of references (see [example of refs.dat file][vizier-refsdat-example])
- Time measurements: this allows for time comparisons, for example with [Time MOCs][aladin-time-moc] in Aladin
- Solar system information: it will be added to the VizieR [B/planets][vizier-bplanets] catalogue and populate the [VESPA][vespa] site


<!-- VizieR catalogue as iframe-->
Interactive window: VizieR catalogue landing page, example for Gaia DR3 Part 1 (VizieR name: [I/355][vizier-table-gaia-dr3]).
<iframe src="https://cdsarc.cds.unistra.fr/viz-bin/cat/I/355#/article" 
title="VizieR catalogue ingested: example Gaia DR3 Part 1." 
style="border: 1px solid black; width: 95%; height: 1200px; 
overflow: hidden; display: block; "
allowfullscreen="" allow="autoplay" data-external="1"></iframe>



<!--  ----------------------------------------- -->
<!--            VizieR and VO tools             -->
<!--  ----------------------------------------- -->
## VizieR catalogue and CDS tools

Once a catalogue is ingested in VizieR, one can access a range of tools:

- Query the [VizieR table(s)][vizier-table-search]
- Access to the [FTP][vizier-ftp] (archived VizieR tables as described by the ReadMe)
- Query VizieR table(s) using [TAP/SQL][vizier-tap]
- Perform a fast [cross-match identification][xmatch-home] between VizieR tables or Simbad
- Load your tables in [Aladin][aladin-home]
- Plot [photometry ("SED")][vizier-sed] including all VizieR 
- Query VizieR [associated data][vizier-assoc-data] (images, spectra)   
- Query all VizieR catalogues using [CDS Python package][vizier-api]
- VizieR tables with astronomical objects can be processed in [SIMBAD][simbad-home].


![Figure: VizieR catalogues accessible through CDS services](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_tools_and_vo__logos.svg){alt="Figure: VizieR and the interoperability with the CDS services. The full list of services is described just above."}
 

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
- Step in the VO: interoperability with other tools, e.g.
	- Load your data as a VO Table using [TOPCAT][topcat]
	- Visualize a spectrum using [CASSIS][cassis]
	- Analyze a spectrum using [Splat][splat]
	- Analyze your data using [astroquery][astroquery]
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
	- Dedicated **indexations**
	- Quality and a good data **description**
	- Generate **persistent identifier** (bibcode, DOI) for citation
	- Data are available through the [Virtual Observatory (VO)][ivoa-link] services
	- Data can be queried by various means (simple search, TAP, Python ...) and retrieved in different format (ASCII, Fits, VOTable ...)
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


<!--  ----------------------------------------- -->
<!-- Transform link a/href with target="_blank" -->
<!-- Open them in a new window			-->
<!--  ----------------------------------------- -->
<script>
document.querySelectorAll('#main-content a:not([target])').forEach(link => link.setAttribute('target', '_blank'))
</script>

