---
title: "Why distribute your data through VizieR?"
teaching: 10
exercises: 2
---

:::::::::::::::::::::::::::::::::::::: questions 

- How and where to publish your data?
- What kind of data can be published (tables, images) ?
- Do and don't when publishing data?
- What are the FAIR principles?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Be aware of the Findable, Accessible, Interoperable and Reusable (FAIR) principles, when preparing your data and its metadata.
- Be aware of how to publish your data in the existing and new Open Science systems,  keeping in mind the Virtual Observatory (VO) standards.

::::::::::::::::::::::::::::::::::::::::::::::::



<!--  ----------------------------------------- -->
<!--            VizieR description              -->
<!--  ----------------------------------------- -->
<!-- Source: https://vizier.cds.unistra.fr/index.gml -->
## What is VizieR?

[VizieR][vizier-home] provides the most complete library of published astronomical catalogues - tables and associated data - with verified and enriched data, accessible via multiple interfaces. Query tools allow the user to select relevant data tables and to extract and format records matching given criteria. Currently, over 23 000 catalogues are available. 

<!--
![VizieR homepage](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_homepage_may2023.png){alt="Screenshot: VizieR homepage, from May 2023"}
-->
![VizieR homepage](file:///home/agonneau/Programs/Github/a-FAIR-journey-for-astronomical-data/episodes/images/vizier_homepage_may2023.png){alt="Screenshot: VizieR homepage, from May 2023"}

VizieR was initially started as a joint effort of CDS (Centre de Données astronomiques de Strasbourg) and ESA-ESRIN (Information Systems Division), and is now fully managed by CDS. VizieR has been available since 1996, and was described in a [paper published in 2000][vizier-first-publi].

Note that VizieR does not contain all available online catalogues: some catalogues are not suitable and some less frequently used catalogues have not yet been incorporated into the VizieR database. The full list of catalogues is available from there: [Catalogue collection page][vizier-catalogue-collection].

<!--
![VizieR Catalogue collection page](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_catalogue_collection_may2023.png){alt="Screenshot: VizieR Catalogue collection page, from May 2023"}
-->
![VizieR Catalogue collection page](file:///home/agonneau/Programs/Github/a-FAIR-journey-for-astronomical-data/episodes/images/vizier_catalogue_collection_may2023.png){alt="Screenshot: VizieR Catalogue collection page, from May 2023"}



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

<!--
![VizieR: Example catalogue](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_catalogue_example_may2023.png){alt="Screenshot: Example catalogue VizieR, from May 2023"}
-->
![VizieR: Example catalogue](file:///home/agonneau/Programs/Github/a-FAIR-journey-for-astronomical-data/episodes/images/vizier_catalogue_example_may2023.png){alt="Screenshot: Example catalogue VizieR, from May 2023"}


<!--  ----------------------------------------- -->
<!--            VizieR and VO                   -->
<!--  ----------------------------------------- -->
## VizieR data are available through the Virtual Observatory (VO)

Once a catalogue ingested in VizieR, one can access a range of tools:

- Query the VizieR table(s)
- Access to the FTP (archived tables as described by the ReadMe)
- Query VizieR table(s) using TAP/SQL
- Fast cross-match identification between VizieR tables or Simbad
-  

<!-- 
![VizieR and VO tools, data from 2021 (**TO BE UPDATED**)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_tools_from_2021.png){alt="Figure: VizieR and VO tools, data from 2021"}
-->
![VizieR and VO tools, data from 2021 (**TO BE UPDATED**)](file:///home/agonneau/Programs/Github/a-FAIR-journey-for-astronomical-data/episodes/images/vizier_tools_from_2021.png){alt="Figure: VizieR and VO tools, data from 2021"}


<!-- 
![Catalogues outputs in VizieR, data from 2021 (**TO BE UPDATED**)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/catalogue_output_vizier_from_2021.png){alt="Figure: Catalogue ingested in Vizier, data from 2021"}
-->
![Catalogues outputs in VizieR, data from 2021 (**TO BE UPDATED**)](file:///home/agonneau/Programs/Github/a-FAIR-journey-for-astronomical-data/episodes/images/catalogue_output_vizier_from_2021.png){alt="Figure: Catalogue ingested in Vizier, data from 2021"}



<!--  ----------------------------------------- -->
<!--            Keypoints                       -->
<!--  ----------------------------------------- -->
<!-- Source: https://cdsarc.cds.unistra.fr/vizier.submit/publication-notes.html#section1 -->
## Benefits of using VizieR 

::::::::::::::::::::::::::::::::::::: keypoints

- **Data preservation**: The CDS has been awarded the [Core Trust Seal][cts].
- **Discovery**: Take advantage of the VizieR services allowing for the discovery, and a good data visibility
	- [VizieR][vizier-data-search] data are available through the [Virtual Observatory (VO)][ivoa-link]
		- Load tables using [TOPCAT][topcat] or [Aladin][aladin-home]
		- Access to spectra/images or time series:
			- Load spectra using [CASSIS][cassis] or [Splat][splat]
			- Load images in [Aladin][aladin-home]
	- Query tables using ADQL/SQL with [TAPVizieR][tap-vizier]
	- The [VizieR Photometry viewer][vizier-sed] is another output using tables for which filters are assigned to create SEDs.
- **Simbad**: VizieR tables with astronomical objects can be processed in [SIMBAD][simbad-home].
- **[CDS Cross-match][xmatch-home]**: merge tables according to positions.

::::::::::::::::::::::::::::::::::::::::::::::::




Other points (from Gilles):

- Step in search engine:
	- registry VO
	- Eudat
	- EOSC
	- ADS
- Step in the VO: interoperability with other tools:
	- CASSIS
	- Topcat
	- astroquery
- Added metadata:
	- UCD (VO)
	- Keywords (UAT)
	- Protocol (ADQL)
	- DOI (Citation)
	- Bibcode
	- MOC
- Visualization enabled:
	- Plots
	- Links



<!--  ----------------------------------------- -->
<!--            Other images                       -->
<!--  ----------------------------------------- -->
<!-- Source: https://cdsarc.cds.unistra.fr/vizier.submit/publication-notes.html#section1 -->
## Other images ???

<!--
![Large collection of astronomical catalogues from VizieR, data from 2021 (**TO BE UPDATED**)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_collection_from_2021.png){alt="Figure: Catalogues / authors overview from VizieR, data from 2021"}
-->
![Large collection of astronomical catalogues from VizieR, data from 2021 (**TO BE UPDATED**)](file:///home/agonneau/Programs/Github/a-FAIR-journey-for-astronomical-data/episodes/images/vizier_collection_from_2021.png){alt="Figure: Catalogues / authors overview from VizieR, data from 2021"}



<!--  ----------------------------------------- -->
<!-- 		Link references			-->
<!--  ----------------------------------------- -->
[cassis]: http://cassis.irap.omp.eu/?page=cassis
[cts]: https://www.coretrustseal.org/
[ivoa-link]: https://www.ivoa.net/
[splat]: http://star-www.dur.ac.uk/~pdraper/splat/splat.html
[topcat]:  http://www.starlink.ac.uk/topcat/
<!-- -->
[aladin-home]: http://aladin.cds.unistra.fr/aladin.gml
[simbad-home]: http://simbad.cds.unistra.fr/simbad/
[xmatch-home]: http://cdsxmatch.u-strasbg.fr/
[vizier-home]: https://vizier.cds.unistra.fr/index.gml
[tap-vizier]: http://tapvizier.cds.unistra.fr/adql/
[vizier-data-search]: https://vizier.cds.unistra.fr/viz-bin/VizieR
[vizier-catalogue-collection]: https://cdsarc.cds.unistra.fr/viz-bin/Cat?menu=on
[vizier-first-publi]: https://ui.adsabs.harvard.edu/abs/2000A%26AS..143...23O/abstract
[vizier-make-your-data-visible]: https://vizier.cds.unistra.fr/vizier/submit/Make_your_data_visible.pdf
[vizier-publi-data-home]: https://vizier.cds.unistra.fr/vizier/submit.htx
[vizier-publi-notes-help]: https://cdsarc.cds.unistra.fr/vizier.submit/publication-notes.html
[vizier-sed]: http://vizier.cds.unistra.fr/vizier/sed/
[vizier-submit-data-help]: https://cdsarc.cds.unistra.fr/vizier.submit/help.html
