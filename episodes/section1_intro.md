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
<!-- 		Overview 			-->
<!--  ----------------------------------------- -->
## Overview

This course is based on [*Preparing and Submitting Tabular Data*][vizier-publi-data-home] (VizieR website). 


<!-- The CDS and other astronomical data centers are storing and distributing the astronomical data to promote their usage primarily by professional astronomers.
In order to ensure the scientific quality of the data, we therefore require that the data are related to a publication in a refereed journal, either as tables or catalogues actually published, or as a paper describing the data and their context. -->







<!--  ----------------------------------------- -->
<!--            Keypoints                       -->
<!--  ----------------------------------------- -->
<!-- Source: https://cdsarc.cds.unistra.fr/vizier.submit/publication-notes.html#section1 -->
## Summary 

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
- **CDS Cross-match**: merge tables according to positions.

::::::::::::::::::::::::::::::::::::::::::::::::



<!--  ----------------------------------------- -->
<!-- 		Documentation 			-->
<!--  ----------------------------------------- -->
## More documentation (from Vizier)

- [Preparing and Submitting Tabular Data][vizier-publi-data-home]
- [VizieR catalogue upload generalities][vizier-publi-notes-help]
- [The submitting VizieR page documentation][vizier-submit-data-help]





<!--  ----------------------------------------- -->
<!--  ----------------------------------------- -->
<!--  ----------------------------------------- -->
## *Ideas for the website* 

1.1 - Publishing your data

1.2 - Do and don’t // FAIR principles 

- Findable, Accessible, Interoperable, Reusable

- Best practices for preparation of data and its metadata. 

1.3 - Something about the different types of data ? (tables, images, spectra, Hips, MOCs, simulation outputs, models… and how they fit in this path)

- Add cheatsheets FAIR principles / publishing data



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
[tap-vizier]: http://tapvizier.cds.unistra.fr/adql/
[vizier-data-search]: https://vizier.cds.unistra.fr/viz-bin/VizieR
[vizier-sed]: http://vizier.cds.unistra.fr/vizier/sed/
[vizier-publi-data-home]: https://vizier.cds.unistra.fr/vizier/submit.htx
[vizier-publi-notes-help]: https://cdsarc.cds.unistra.fr/vizier.submit/publication-notes.html
[vizier-submit-data-help]: https://cdsarc.cds.unistra.fr/vizier.submit/help.html
