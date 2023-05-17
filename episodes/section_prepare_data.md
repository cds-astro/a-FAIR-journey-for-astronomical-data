---
title: "Preparing your data"
teaching: 10
exercises: 2
---


:::::::::::::::::::::::::::::::::::::: questions 

- What kind of data can be published (tables, images) ?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Be aware of  ...

::::::::::::::::::::::::::::::::::::::::::::::::


![Data journey from a publication to VizieR: step Prepare (part 2)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_paths_prepare_part2.png){alt="Summary Data journey from a publication to VizieR, step Prepare, part 2"}


<!--  ----------------------------------------- -->
<!-- 		Type of data 			-->
<!--  ----------------------------------------- -->
## Overview

In order to facilitate the usability of the data, and to allow their processing by the data centers, we at CDS require that:

- the data are *described* accurately enough to allow an unambiguous interpretation of the data, as well as a comprehension of the context in which the data were acquired and/or processed; a single ascii file, named *ReadMe*, is designed for this role.
- the data are in a format which allows their usage by tools currently in usage in our discipline - normally *flat ascii files*; other formats can be accepted, but are converted into flat files.


The present course just tries to answer to some frequently asked question about how to prepare the data for their inclusion in the Data Center documents.

A full description of the standard conventions used for the documentation of the catalogues is available from [there][vizier-standard-convention].


The following data types are accepted:

- Tables
- Associated data : images, spectra, sed (**still true???** -- AG), time series, cube
- Other types: MOC / Hips (**REALLY???** -- AG)




<!--  ----------------------------------------- -->
<!-- 		Tables	 			-->
<!--  ----------------------------------------- -->
<!-- Source: https://cdsarc.cds.unistra.fr/vizier.submit/publication-notes.html#section2 -->
## Tables

![Example VizieR table](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_table_example.png){alt="Example of VizieR table ingested"}


<!--  ----------------------------------------- -->
### Accepted format

The following formats are welcome: 

- Machine-Readable Tables (MRT / FORTRAN format)
- TSV, CSV: TSV (tab-separated values) or CSV (comma-separated values) files containing a first line with column description is accepted
- ASCII aligned files
- FITS files
- VOTable

Note: zip and gzip compression are allowed. Archives should not contain directories.

The [new submit web application][vizier-submit-login] allows different formats for tables and helps you to ingest your data.


**Is is true?? -- From AG==>
Some other data formats can be accepted, but are converted into flat files (ascii??): latex, FITS, or TSV / CSV.**




<!--  ----------------------------------------- -->
### What cannot be used

Postscript or word/excel files.



<!--  ----------------------------------------- -->
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

![Example VizieR associated data (spectra)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_saada_example_spectra.png){alt="Example of VizieR spectra ingested"}

### Accepted format

Reusable file formats for associated:

| Product type  		| Accepted format      |
| -------------			| :------------------: | 
|images (2-D data)		| FITS		       |
|spectra, sed (1-D data)	| FITS, VOTable, ASCII |
|time series  			| ASCII, FITS          |
|cube				| FITS		       |


**Note: Only FITS files will be indexed and accessible through the [VizieR associated data service][vizier-assoc-data] and through the Virtual Observatory**

**Question -- From AG**: Are the data all converted to FITS?


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

List of important keywords to be included:

- **Positions**
	- target name
	- coordinates: full WCS (World Coordinate System) is recommended including the projection, the center ... (FITS cards: CRVAL, CDELT, CDi_j, CTYPE, CUNIT, CRPIX..)
- **Wavelength(s)** of observations
	- full WCS recommended including units (ex: IRAF WAT cards)
- Observation **date**
- **Telescope**: instrument and Facility


For the sake of clarity and simplicity, we ask the authors, whenever possible, to stick to the "1 item = 1 file" rule, i.e. 1 star spectrum per file, for instance. In this simplest context, fits files should ideally also have only 1 HDU. 



<!--  ----------------------------------------- -->
<!-- 		Other types			-->
<!--  ----------------------------------------- -->
## Other types??

- MOC
- Hips



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

Quiz: ***List of good / bad examples  => Quiz: yes and no answer***

**Idea:Test those names on the VizieR website**

:::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::: instructor

Show some good and bad examples of filenames 

::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::::


::::::::::::::::::::::::::::::::::::: challenge

## Quiz: Are these filenames correct or not?


```
[Q1] 'my_awesome_file.fit'
[Q2] '998bla.dat'
[Q2] 'myfile.jpg'
[Q4] 'table.dat'
[Q5] 'table&data.dat'
```

:::::::::::::::::::::::: solution

## Output

```
[1] "No: too long"
[2] "No: ??"
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

![VizieR FITS validator tool page](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_fits_validator_may2023.png){alt="Screenshot: VizieR FITS validator tool, from May 2023"}



<!--  ----------------------------------------- -->
<!--            Summary	                        -->
<!--  ----------------------------------------- -->
## Type of data accepted by VizieR: summary


::::::::::::::::::::::::::::::::::::: keypoints

Data types accepted:

- Tables (including at least a ReadMe file)
- Associated data : images, spectra, sed (**still true???** -- AG), time series, cube
	
Preferred formats:

- Tables should be preferably written as machine-readable tables (MRT)
- For the associated data, the FITS format is the preferred solution

::::::::::::::::::::::::::::::::::::::::::::::::



<!--  ----------------------------------------- -->
<!-- 		Documentation 			-->
<!--  ----------------------------------------- -->
## More information 

- [Standard for Documentation of Astronomical Catalogues (from VizieR website)][vizier-standard-convention]



<!--  ----------------------------------------- -->
<!--            Next Chapters                   -->
<!--  ----------------------------------------- -->
## Next chapters

In the next chapters, you will learn how to submit your data, and finally how to search your data using the EOSC tools. 



<!--  ----------------------------------------- -->
<!-- 		Link references			-->
<!--  ----------------------------------------- -->
[fits-nasa]: https://fits.gsfc.nasa.gov/
<!-- -->
[vizier-cat-2-description]: https://vizier.cds.unistra.fr/vizier/catstd/catstd-2.htx
[vizier-fits-validator]: https://cdsarc.cds.unistra.fr/vizier.submit/fitsvalidator.html
[vizier-submit-login]: https://cdsarc.cds.unistra.fr/vizier.submit/index.html
[vizier-standard-convention]: https://vizier.cds.unistra.fr/vizier/doc/catstd.htx

