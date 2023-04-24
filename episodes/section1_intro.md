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
<!-- Source: https://vizier.cds.unistra.fr/vizier/submit.htx -->
## Overview

The CDS and other astronomical data centers are storing and distributing the astronomical data to promote their usage primarily by professional astronomers.

In order to ensure the scientific quality of the data, we therefore require that the data are related to a publication in a refereed journal, either as tables or catalogues actually published, or as a paper describing the data and their context.


For a quick view of the guidelines and recommandations for publishing your data at CDS, please have a look at the ["Make your data visible" brochure][vizier-make-your-data-visible].


See also the Best Practices for Data Publication in the Astronomical Literature (T.Chen, 2022). The article is dedicated for authors, and is a basis of good practices expected in journals and data-centers.

In order to facilitate the usability of the data, and to allow their processing by the data centers, we require that:

- the data are *described* accurately enough to allow an unambiguous interpretation of the data, as well as a comprehension of the context in which the data were acquired and/or processed; a single ascii file, named *ReadMe*, is designed for this role.
- the data are in a format which allows their usage by tools currently in usage in our discipline — normally *flat ascii files*; other formats can be accepted, but are converted into flat files.

A full description of the standard conventions used for the documentation of the catalogues is available at URL http://cds.unistra.fr/doc/catstd.htx. The present document just tries to answer to some frequently asked question about how to prepare the data for their inclusion in the Data Center documents. 



<!--  ----------------------------------------- -->
<!--            VizieR stats                    -->
<!--  ----------------------------------------- -->
<!-- Source: -->
## Some statistics

Number of catalogues ingested: https://vizier.cds.unistra.fr/index.gml (top of the page)

Catalogue per journal: https://vizier.cds.unistra.fr/vizier/welcome/vizierbrowse.gml?designation



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
<!-- 		Documentation 			-->
<!--  ----------------------------------------- -->
## More documentation (from Vizier)

- [Preparing and Submitting Tabular Data][vizier-publi-data-home]
- [Upload File to VizieR: generalities][vizier-publi-notes-help]
- [The submitting VizieR page documentation][vizier-submit-data-help]




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
[tap-vizier]: http://tapvizier.cds.unistra.fr/adql/
[vizier-data-search]: https://vizier.cds.unistra.fr/viz-bin/VizieR
[vizier-sed]: http://vizier.cds.unistra.fr/vizier/sed/
[vizier-publi-data-home]: https://vizier.cds.unistra.fr/vizier/submit.htx
[vizier-publi-notes-help]: https://cdsarc.cds.unistra.fr/vizier.submit/publication-notes.html
[vizier-submit-data-help]: https://cdsarc.cds.unistra.fr/vizier.submit/help.html
[vizier-make-your-data-visible]: https://vizier.cds.unistra.fr/vizier/submit/Make_your_data_visible.pdf
