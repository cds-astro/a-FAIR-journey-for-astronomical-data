---
title: "Why distribute your data through VizieR?"
teaching: 10
exercises: 2
---

:::::::::::::::::::::::::::::::::::::: questions 

- What is VizieR?
- What is a VizieR catalogue?
- How is VizieR interoperable?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Be aware of the benefits of publishing your data in VizieR

::::::::::::::::::::::::::::::::::::::::::::::::



<!--  ----------------------------------------- -->
<!--            VizieR description              -->
<!--  ----------------------------------------- -->
<!-- Source: https://vizier.cds.unistra.fr/index.gml -->
## What is VizieR?

[VizieR][vizier-home] provides the most complete library of published astronomical catalogues - tables and associated data - with verified and enriched data, accessible via multiple interfaces. Query tools allow the user to select relevant data tables and to extract and format records matching given criteria. Currently, over 23 000 catalogues are available. 

![VizieR homepage](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_homepage_may2023.png){alt="Screenshot: VizieR homepage, from May 2023"}

VizieR was initially started as a joint effort of [CDS (Centre de Données astronomiques de Strasbourg)][cds-home] and ESA-ESRIN (Information Systems Division), and is now fully managed by CDS. VizieR has been available since 1996, and was described in a [paper published in 2000][vizier-first-publi].

Note that VizieR does not contain all available online catalogues: some catalogues are not suitable and some less frequently used catalogues have not yet been incorporated into the VizieR database. The full list of catalogues is available from there: [Catalogue collection page][vizier-catalogue-collection].

![VizieR Catalogue collection page](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_catalogue_collection_may2023.png){alt="Screenshot: VizieR Catalogue collection page, example for Gaia DR3, from May 2023"}



<!--  ----------------------------------------- -->
<!--            VizieR catalogue                -->
<!--  ----------------------------------------- -->
<!-- Source: Presentation Gilles AAS 2021 -->
## What is a VizieR catalogue?

Looking at the catalogue level:

- A set of documented tables (including a ReadMe file)
- An indexation by keywords, authors, date ...
- A global indexation by position
- Citation capability (bibcode or DOI)

Optionally contains:

- Photometry assignment to populate the VizieR SED service
- FITS Spectra, images and plots
- HiPS files (Hierarchical Progressive Surveys) 

![VizieR: Example catalogue ingested](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_catalogue_example_may2023.png){alt="Screenshot: Example catalogue VizieR, from May 2023"}



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
- Query VizieR [associated data][vizier-assocdata] (images, spectra, timeseries)   
- Load your data as a VO Table using [TOPCAT][topcat]
- Query all VizieR catalogues using [CDS Python package][vizier-api]
- VizieR tables with astronomical objects can be processed in [SIMBAD][simbad-home].


![VizieR catalogues accessible through many VO tools](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_tools_and_vo.png){alt="Figure: VizieR and other VO tools overview"}
 

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
	- [European Open Science Cloud (EOSC) Future][eosc-portal]
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

In the next chapters, you will learn what type of data can be published, how to prepare and publish them, and finally how to search your data using the EOSC tools. 

![Full data journey from a publication to VizieR](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_paths.png){alt="Summary Data journey from a publication to VizieR, full path"}


<!--  ----------------------------------------- -->
<!-- 		Link references			-->
<!--  ----------------------------------------- -->
[topcat]:  http://www.starlink.ac.uk/topcat/
[ivoa-registry]: http://rofr.ivoa.net/
[eudat]: https://www.eudat.eu/
[ads]: https://ui.adsabs.harvard.edu/classic-form
[eosc-portal]: https://eosc-portal.eu/
[cassis]: http://cassis.irap.omp.eu/?page=cassis
[splat]: http://star-www.dur.ac.uk/~pdraper/splat/splat.html
[cts]: https://www.coretrustseal.org/
[ivoa-link]: https://www.ivoa.net/
<!-- -->
[cds-home]: https://cds.unistra.fr/
[aladin-home]: http://aladin.cds.unistra.fr/aladin.gml
[xmatch-home]: http://cdsxmatch.u-strasbg.fr/
<!-- -->
[vizier-home]: https://vizier.cds.unistra.fr/index.gml
[vizier-first-publi]: https://ui.adsabs.harvard.edu/abs/2000A%26AS..143...23O/abstract
[vizier-catalogue-collection]: https://cdsarc.cds.unistra.fr/viz-bin/Cat?menu=on
[vizier-table-search]: https://vizier.cds.unistra.fr/viz-bin/VizieR
[vizier-ftp]: https://cdsarc.cds.unistra.fr/ftp/
[vizier-tap]: http://tapvizier.cds.unistra.fr/adql/
[vizier-sed]: http://vizier.cds.unistra.fr/vizier/sed/
[vizier-assocdata]: https://cdsarc.cds.unistra.fr/assocdata/
[vizier-api]: https://github.com/cds-astro/cds.cdsclient/
<!-- -->
<!-- Not used -->
<!-- -->
[simbad-home]: http://simbad.cds.unistra.fr/simbad/

[vizier-make-your-data-visible]: https://vizier.cds.unistra.fr/vizier/submit/Make_your_data_visible.pdf
[vizier-publi-data-home]: https://vizier.cds.unistra.fr/vizier/submit.htx
[vizier-publi-notes-help]: https://cdsarc.cds.unistra.fr/vizier.submit/publication-notes.html
[vizier-submit-data-help]: https://cdsarc.cds.unistra.fr/vizier.submit/help.html

