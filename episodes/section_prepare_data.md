---
title: "Preparing your data"
teaching: 3
exercises: 1
---


:::::::::::::::::::::::::::::::::::::: questions 

- What kind of data can be submitted to VizieR?
- Which formats are accepted?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Be aware of the type of data accepted in VizieR
- Keep some FAIR principles in mind when preparing the data

::::::::::::::::::::::::::::::::::::::::::::::::



<!--  ----------------------------------------- -->
<!-- 		Type of data 			-->
<!--  ----------------------------------------- -->
## Overview

In order to facilitate the usability of the data, and to allow their processing by the data centers, we at CDS require that:

- the data are *described* accurately enough to allow an unambiguous interpretation of the data, as well as a comprehension of the context in which the data were acquired and/or processed; a single ascii file, named *ReadMe*, is designed for this role.
- the data are in a format which allows their usage by tools currently in usage in our discipline - normally *flat ascii files*; other formats can be accepted, but are converted into flat files.


The following data types are accepted:

- Tables
- Associated data : images, spectra, SED, time series, cube


In this chapter, we will answer to some frequently asked questions about how to prepare the data for their inclusion in VizieR.


![Journey from a publication to EOSC: second step of the journey - step preparation of the data **(WARNING: OLD image to UPDATE)**](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/old__lighthouse_v1/step2.svg){alt="Figure -- Summary data journey from a publication to VizieR and then EOSC: second step of the journey - step preparation of the data, right after - step data published in a refereed paper"}




<!--  ----------------------------------------- -->
<!-- 		Tables	 			-->
<!--  ----------------------------------------- -->
<!-- Source: https://cdsarc.cds.unistra.fr/vizier.submit/publication-notes.html#section2 -->
## Tables

Tables are the main data types accepted. An [example of ingested table][vizier-table-gaia-dr3] is shown below. 

![Example of a VizieR table ingested: catalogue Gaia DR3 - ref I/355/gaiadr3 (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_table_example.png){alt="Screenshot: Example of a VizieR table ingested. The figure shows the first 20 rows for the table 'I/355/gaiadr3'."}



<!--  ----------------------------------------- -->

The following formats are welcome: 

:::::::::::::::::::::::::::::::::::::: prereq

### Accepted format

- Machine-Readable Tables (MRT / FORTRAN format)
- TSV, CSV: TSV (tab-separated values) or CSV (comma-separated values) files containing a first line with column description is accepted
- ASCII aligned files
- FITS files
- VOTable

Note: zip and gzip compression are allowed. Archives should not contain directories.

:::::::::::::::::::::::::::::::::::::::::::::::::::


The [new submit web application][vizier-submit-login] allows different formats for tables and helps you to ingest your data.


<!--  ----------------------------------------- -->
### What cannot be used

Postscript or word/excel files.



<!--  ----------------------------------------- -->
### Checklist when creating a table

:::::::::::::::::::::::::::::::::::::: checklist

- An explanation is given for all the columns (at least a clear label; at best, few words of explanation).
- Units are given for all the columns (when relevant).
- For tables with sources, give coordinates as accurate as possible:
	- A bonus would be to have their uncertainty.
	- Another bonus would be to have their wavelength.
- As recommended by the IAU, a non-altered name is given for the sources (in addition to the coordinates).
- It is really much better to stick to the same object name from a table to another.
- One column is homogeneous, i.e. does not mix different measurements having different units or errors with limit values or flags.
- If the measurements come from other papers, the references to those papers should be explicitly given using the bibcode.

:::::::::::::::::::::::::::::::::::::::::::::::::::

Following this checklist will help improving the efficiency of the ingestion in VizieR and also the visibility and reusability of your data :).


<!--  ----------------------------------------- -->
<!-- 		Associated date			-->
<!--  ----------------------------------------- -->
<!-- Source: https://cdsarc.cds.unistra.fr/vizier.submit/publication-notes.html#section3 -->
## Associated data: images, spectra, time series, cube

In addition to the Tables, other data type are associated. 

![Example of VizieR associated data from the Saada page: spectra (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_saada_example_spectra.png){alt="Screenshot: Example of spectra ingested and available through the Saada VizieR page, associated with the catalogue 'J/A+A/589/A36'. "}


Reusable file formats for associated:

:::::::::::::::::::::::::::::::::::::: prereq

### Accepted format

| Product type  		| Accepted format      |
| -------------			| :------------------: | 
|images (2-D data)		| FITS		       |
|spectra, sed (1-D data)	| FITS, VOTable, ASCII |
|time series  			| ASCII, FITS          |
|cube				| FITS		       |


**Note: Although multiple formats are accepted, only FITS files will be indexed and accessible through the [VizieR associated data service][vizier-assoc-data] and through the Virtual Observatory**. 
The other formats will still be accessible through the FTP. 


:::::::::::::::::::::::::::::::::::::::::::::::::::

<!--  ----------------------------------------- -->
### What cannot be used

Postscript or word/excel documents.

GIF or JPEG images.



<!--  ----------------------------------------- -->
### General rules for FITS

In order to index FITS formats as accurately as possible, several basic meta-data are needed, usually readily provided by the telescope software and data processing pipelines such as IRAF and MIDAS, as FITS header keywords.

As a good practice, any FITS header should provide:

- WCS projections for positions and spectral data
- [Standard FITS keywords][fits-nasa] described in the NASA FITS description.


:::::::::::::::::::::::::::::::::::::: checklist

# List of important keywords to be included:

- **Positions**
	- target name
	- coordinates: full WCS (World Coordinate System) is recommended including the projection, the center ... (FITS cards: CRVAL, CDELT, CDi_j, CTYPE, CUNIT, CRPIX..)
- **Wavelength(s)** of observations
	- full WCS recommended including units (ex: IRAF WAT cards)
- Observation **date**
- **Telescope**: instrument and Facility


For the sake of clarity and simplicity, we ask the authors, whenever possible, to stick to the "1 item = 1 file" rule, i.e. 1 star spectrum per file, for instance. In this simplest context, fits files should ideally also have only 1 HDU. 

:::::::::::::::::::::::::::::::::::::::::::::::::::


<!--  ----------------------------------------- -->
<!--       File naming conventions 		-->
<!--  ----------------------------------------- -->
<!-- Source: https://vizier.cds.unistra.fr/vizier/submit.htx  // Section 2 -->
## File naming conventions

According to ISO 9660 standard, file names are restricted to **8 + 3** characters: 

- 8 characters in the set [a-z0-9 _ -], 
- Followed by a dot 
- And an extension made of 3 characters with the following conventions: 
	- **.dat** for data files, 
	- **.fit** for FITS files, 
	- **.tex** for TeX/LaTeX files, 
	- and **.txt** for text files (ascii files containing only printable text).

Full details about the files and directories structures can be found in the [Adopted Standards for Catalogues document][vizier-cat-2-description].



<!--  ----------------------------------------- -->

**Idea:Test those names on the VizieR website**


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
<!--            VizieR FITS validator           -->
<!--  ----------------------------------------- -->
## VizieR FITS validator

You can test your FITS spectra/images with the [VizieR FITS validator tool][vizier-fits-validator] which evaluates the compatibility between your FITS and the asked meta-data. 

This meta-data checking is also completed during the [VizieR submission service][vizier-submit-login].

<!-- VizieR FITS validator as iframe-->
<iframe src="https://cdsarc.cds.unistra.fr/vizier.submit/fitsvalidator.html" 
title="VizieR FITS validator tool webpage" 
style="border: 1px solid black; width: 95%; height: 550px; 
overflow: hidden; display: block; "
allowfullscreen="" allow="autoplay" data-external="1"></iframe>

VizieR FITS validator tool webpage


<!--  ----------------------------------------- -->
<!--            Summary	                        -->
<!--  ----------------------------------------- -->
## Summary: Type of data accepted by VizieR


::::::::::::::::::::::::::::::::::::: keypoints

Data types accepted:

- Tables (including at least a ReadMe file)
- Associated data : images, spectra, SED, time series, cube
	
Preferred formats:

- Tables should be preferably written as machine-readable tables (MRT)
- For the associated data, the FITS format is the preferred solution

::::::::::::::::::::::::::::::::::::::::::::::::



<!--  ----------------------------------------- -->
<!-- 		Documentation 			-->
<!--  ----------------------------------------- -->
## More information 

- [Standard for Documentation of Astronomical Catalogues (from VizieR website)][vizier-standard-convention]

A full description of the standard conventions used for the documentation of the catalogues is available from [there][vizier-standard-convention].


<!--  ----------------------------------------- -->
<!--            Next Chapters                   -->
<!--  ----------------------------------------- -->
## Next chapters

In the next chapters, you will learn how and where to submit your data, and finally how to search your data using the EOSC tools. 



<!--  ----------------------------------------- -->
<!-- 		Link references			-->
<!--	==> See links.md file			-->
<!--  ----------------------------------------- -->

