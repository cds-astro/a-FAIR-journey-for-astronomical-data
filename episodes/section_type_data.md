---
title: "Which type of data can you send to VizieR?"
teaching: 10
exercises: 2
---

:::::::::::::::::::::::::::::::::::::: questions 

- What kind of data can be published (tables, images) ?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Be aware of  ...

::::::::::::::::::::::::::::::::::::::::::::::::


![Data journey from a publication to VizieR: step Prepare (part 1)](file:///home/agonneau/Programs/Github/a-FAIR-journey-for-astronomical-data/episodes/images/vizier_paths_prepare_part1.png){alt="Summary Data journey from a publication to VizieR, step Prepare, part 1"}

<!--  ----------------------------------------- -->
<!-- 		Type of data 			-->
<!--  ----------------------------------------- -->
## Overview

### 1. Tables
 
### 2. Associated data : images, time series, spectra

### 3. Other types: MOC / Hips



<!--  ----------------------------------------- -->
<!-- 		Tables	 			-->
<!--  ----------------------------------------- -->
<!-- Source: https://cdsarc.cds.unistra.fr/vizier.submit/publication-notes.html#section2 -->
## Tables


### Format

The following formats are welcome: 

- machine-readable tables (FORTRAN format, see the basic conventions)
- csv files
- tsv files
- aligned ASCII files
- FITS files


### Web application

The [new submit web application][vizier-submit-login] allows different formats for tables and helps you to ingest your data.


### Checklist when creating a table

- An explanation is given for all the columns (at least a clear label; at best, few words of explanation)
- Units are given for all the columns (when relevant)
- For tables with sources, give coordinates as accurate as possible:
	- A bonus would be to have their uncertainty
	- Another bonus would be to have their wavelength
- As recommended by the IAU, a non-altered name is given for the sources (in addition to the coordinates)
- It is really much better to stick to the same object name from a table to another
- One column is homogeneous, i.e. does not mix different measurements having different units or errors with limit values or flags.
- If the measurements come from other papers, the references to those papers should be explicitly given using the bibcode.

Following this checklist will help improving the efficiency of the ingestion in VizieR and also the visibility and reusability of your data :).


<!--  ----------------------------------------- -->
<!-- 		Associated date			-->
<!--  ----------------------------------------- -->
<!-- Source: https://cdsarc.cds.unistra.fr/vizier.submit/publication-notes.html#section3 -->
## Associated data: images, time series, spectra

### Format

Reusable file formats for associated:

| Product type  | Accepted format      |
| -------------	| :------------------: | 
| time series  	| ASCII, FITS          |
|images		| FITS		       |
|cube		| FITS		       |
|spectra, sed	| FITS, VOTable, ASCII |


**Note: Only FITS files will be indexed and accessible through the [VizieR associated data service][vizier-assoc-data] and through the Virtual Observatory**


### General rules for FITS

In order to index FITS formats as accurately as possible, several basic meta-data are needed, usually readily provided by the telescope software and data processing pipelines such as IRAF and MIDAS, as FITS header keywords.

As a good practice, any FITS header should provide:

- WCS projections for positions and spectral data
- [standard FITS keywords][fits-nasa] described in the NASA FITS description.

For the sake of clarity and simplicity, we ask the authors, whenever possible, to stick to the "1 item = 1 file" rule, i.e. 1 star spectrum per file, for instance. In this simplest context, fits files should ideally also have only 1 hdu. An automatic, supervised detection of the meta-data is available in the new VizieR submit page. It resolves the most popular projections, data reduction software (IRAF, MIDAS) headers and recognizes FITS keywords given in the NASA FITS description.


### Small checklist for providing correct headers

 - **Positions**
	- target name
	- coordinates: full WCS is recommended including the projection, the center ... (FITS cards: CRVAL, CDELT, CDi_j, CTYPE, CUNIT, CRPIX..)
- **Wavelength(s)** of observations
	- full WCS recommended including units (ex: IRAF WAT cards)
- Observation **date**
- **Telescope**: instrument and Facility

If your associated data are correctly described, then they will be provided through the [VizieR associated data web page][vizier-assoc-page] and through the Virtual Observatory ([CASSIS][cassis], [Splat][splat], [Aladin][aladin-home]).



<!--  ----------------------------------------- -->
<!-- 		Other types			-->
<!--  ----------------------------------------- -->
## Other types


## Summary

<!--  ----------------------------------------- -->
<!--            Next Chapters                   -->
<!--  ----------------------------------------- -->
## Next chapters

In the next chapters, you will learn what type of data 



<!--  ----------------------------------------- -->
<!-- 		Link references			-->
<!--  ----------------------------------------- -->
[cassis]: http://cassis.irap.omp.eu/?page=cassis
[fits-nasa]: https://fits.gsfc.nasa.gov/
[splat]: http://star-www.dur.ac.uk/~pdraper/splat/splat.html
<!-- -->
[aladin-home]: http://aladin.cds.unistra.fr/aladin.gml
[vizier-publi-data-home]: https://vizier.cds.unistra.fr/vizier/submit.htx
[vizier-publi-notes-help]: https://cdsarc.cds.unistra.fr/vizier.submit/publication-notes.html
[vizier-submit-login]: https://cdsarc.cds.unistra.fr/vizier.submit/index.html
[vizier-submit-data-help]: https://cdsarc.cds.unistra.fr/vizier.submit/help.html
[vizier-assoc-data]: https://cdsarc.cds.unistra.fr/assocdata/
[vizier-fits-validator]: https://cdsarc.cds.unistra.fr/vizier.submit/fitsvalidator.html
