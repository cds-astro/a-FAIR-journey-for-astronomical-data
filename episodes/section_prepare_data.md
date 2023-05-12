---
title: "Preparing your data"
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



![Data journey from a publication to VizieR: step Prepare (part 3)](file:///home/agonneau/Programs/Github/a-FAIR-journey-for-astronomical-data/episodes/images/vizier_paths_prepare_part3.png){alt="Summary Data journey from a publication to VizieR, step Prepare, part 3"}


<!--  ----------------------------------------- -->
<!-- 		Preparing Data Files		-->
<!--  ----------------------------------------- -->
<!-- Source: https://vizier.cds.unistra.fr/vizier/submit.htx  // Section 2 -->
## How to prepare the Data files?

It is assumed that each component of the data set is stored in a *file*; each file can represent a *table*, a *spectrum* (1-D data), or an *image* (2-D data). As a general rule, plain ascii data files (also called *flat files*) — are preferred, simply because such files can always be processed. More explicitely, the following formats can be used:

- for tables and catalogues: **ascii** (simple flat files), with details about their structures (description of columns) detailed in the ReadMe file. Some other data formats can be accepted, but are converted into flat files: latex, FITS, or TSV / CSV. TSV (tab-separated values) and CSV (character-separated values), are a presentation where a dedicated character (the tab in TSV, or a punctuation in CSV, typically the semi-colon) is used as a column separator; this is one of the formats available for the output of spreadsheets.

**What cannot be used**: postscript or word/excel processing internal documents.


- for spectra (1-D data): either FITS file(s), or 2-column ascii tables.

**What cannot be used**: postscript, word/excel documents, GIF or JPEG images.


- for images (2-D data): FITS is the preferred format; for images of the sky, the inclusion of the FITS-WCS (World Coordinate System) parameters describing the conversion between celestial coordinates and pixel position is strongly encouraged.

**What cannot be used**: postscript, word/excel documents.


Therefore: **never postscript files**, postscript is a language designed for printers, not for storing scientific data !

A short word about **file naming conventions**: according to ISO 9660 standard, file names are restricted to **8 + 3** characters: 8 characters in the set [a-z0-9 _ -], followed by a dot and an extension made of 3 characters with the following conventions: **.dat** for data files, **.fit** for FITS files, **.tex** for TeX/LaTeX files, and **.txt** for text files (ascii files containing only printable text).

Full details about the files and directories structures can be found in the [Adopted Standards for Catalogues document][vizier-cat-2-description].

The CDS provides **tools and services** for authors submission :

- build ReadMe and tables: [anafile package][vizier-cdspyreadme]
- FITS spectra/images validation service: [FITS validator][vizier-fits-validator]



<!--  ----------------------------------------- -->
<!--            FITS validator                  -->
<!--  ----------------------------------------- -->
## FITS validator

Test your FITS spectra/images with the [FITS validator][vizier-fits-validator] which evaluates the compatibility between your FITS and the asked meta-data. This meta-data checking can be completed in the [VizieR submission service][vizier-submit-login].





<!--  ----------------------------------------- -->
<!-- 	Fill the Readme description file 	-->
<!--  ----------------------------------------- -->
<!-- Source: https://vizier.cds.unistra.fr/vizier/submit.htx  // Section 3 -->
## How to fill the ReadMe description file?

This file is aimed at describing all data files stored in a catalogued data set, and at providing the necessary explanations and references to the stored material.

All catalogues available at CDS and in associated astronomical data centers have such an associated file, and numerous examples can be found on the [FTP directories][vizier-ftp-cats] at CDS.

A full description of the conventions used in this *ReadMe* file can be found in the [Standards for Astronomical Catalogues][vizier-readme-std], and a template is readily accessible for all journals. A typical illustration could be e.g. [J/A+A/382/389/ReadMe][vizier-readme-example]. Short explanations about how to fill the *ReadMe* file:

- the **volume** and **page** numbers: for papers accepted for publication in A&A, but not yet published, these will be added directly at CDS as soon as we get these from the publisher. For papers accepted for publication in other journals, it is recommended to mail them (to [cats(at)cdsarc.u-strasbg.fr](mailto:cats@cdsarc.u-strasbg.fr)) when you get these details from the publisher.


- the **Keywords**: part lists the following keywords:
	- *ADC\_Keywords* introduces the list of data-related keywords, out of a controlled set
	- *Keywords*:   introduces the list of keywords as in the printed publication

Unlike the *Keywords*:  set which is generally related to the scientific goal of a paper, the *ADC\_Keywords* are stricly related to the tabular material collected in the paper.


- the **Description**: section is expected to describe the *context of the data*, like the instrumentation used or the observing conditions — it therefore differs from the *Abstract* which tends to describe the *scientific results* that the author derived from the data.


- the **File Summary**: section describes the files making up the set: for each file are specified its *filename*, the *length of the longest line* (lrecl), the *number of records* (number of lines), and a *caption* (short title of the file). Lengthy notes can be added if necessary.


- the **Byte-by-byte Description of file**: section describes the structure of each of the data files (files with the *.dat* extension). This description is made in a tabular form, each row describing one field (column) of the data file. The description contains the following columns:
	- the *starting* column of the data field
	- the *format* of the field as a *fortran-like* format:
		- **A***n*	for a character column made of *n* characters;
		- **I***n*	for a column containing an integer number of *n* digits;
		- **F***n.d*	for a column containing a number of width *n* digits and up to *d* digits in the fractional part;
		- **E***n.d*	for a number using the exponential notation;
		- **D***n.d*
	- the [units][vizier-cat-32-units] used in the field; the usage of **SI** units are strongly encouraged, avoid the CGS units (for instance, use **mW/m2** instead of **ergs/s/cm2**).
	- the *label* (heading) of the field, made of a single word (*no embedded blank*); a few [basic conventions][vizier-cat-33-labels] are used for usual parameters (e.g. positions) and related quantities (e.g. mean errors).
	- the *explanations* can start with the following special characters related to some important data characteristics:
		- **\***	(the asterisk)	indicating a [lengthy note][vizier-cat-35-lengthy]
		- **[...]**	(square brackets)	indicating *data ranges*
		- **?**	(question mark)	indicating a possibility of [blank or NULL][vizier-cat-34-optional] (unspecified) values


- the **References**: section contains the necessary references; the usage of the bibcode(**WARNING: link not found**) is strongly encouraged. 

For large sets of references, it is suggested to gather them into a dedicated *reference file* named **refs.dat**.



## Summary


<!--  ----------------------------------------- -->
<!--            Next Chapters                   -->
<!--  ----------------------------------------- -->
## Next chapters

In the next chapters, you will learn what type of data 


<!--  ----------------------------------------- -->
<!-- 		Link references			-->
<!--  ----------------------------------------- -->
[aa-home]: https://www.aanda.org/
[aa-publi-data-cds]: https://www.aanda.org/for-authors/latex-issues/tables
[aa-astro-objects-link]: https://www.aanda.org/for-authors/latex-issues/astronomical-objects-linking-to-databases
<!-- -->
[aas-home]: https://journals.aas.org/
[aas-data-guide]: https://journals.aas.org/data-guide/
<!-- -->
[mnras-home]: https://academic.oup.com/mnras
[mnras-publi-data-cds]: https://academic.oup.com/mnras/pages/General_Instructions#2.7%20Catalogues%20and%20online-only%20material
<!-- -->
[vizier-cat-2-description]: https://vizier.cds.unistra.fr/vizier/catstd/catstd-2.htx
[vizier-cat-32-units]: https://vizier.cds.unistra.fr/vizier/catstd/catstd-3.2.htx
[vizier-cat-33-labels]: https://vizier.cds.unistra.fr/vizier/catstd/catstd-3.3.htx
[vizier-cat-34-optional]: https://vizier.cds.unistra.fr/vizier/catstd/catstd-3.4.htx
[vizier-cat-35-lengthy]: https://vizier.cds.unistra.fr/vizier/catstd/catstd-3.5.htx
[vizier-cdspyreadme]: https://github.com/cds-astro/cds.pyreadme/
[vizier-fits-validator]: https://cdsarc.cds.unistra.fr/vizier.submit/fitsvalidator.html
[vizier-ftp-cats]: http://cdsarc.cds.unistra.fr/ftp/cats/
[vizier-publi-data-home]: https://vizier.cds.unistra.fr/vizier/submit.htx
[vizier-publi-notes-help]: https://cdsarc.cds.unistra.fr/vizier.submit/publication-notes.html
[vizier-readme-std]: https://vizier.cds.unistra.fr/vizier/catstd/catstd-3.1.htx
[vizier-readme-example]: https://cdsarc.cds.unistra.fr/ftp/cats/J/A+A/382/389/ReadMe
[vizier-readme-example-aa]: http://cdsarc.u-strasbg.fr/ftp/cats/J/A+A/ReadMe.txt
[vizier-submit-login]: https://cdsarc.cds.unistra.fr/vizier.submit/index.html
[vizier-submit-data-help]: https://cdsarc.cds.unistra.fr/vizier.submit/help.html
[vizier-submit-old]: http://cdsarc.u-strasbg.fr/viz-bin/Submit
<!-- -->
[viz-astro-data]: https://vizier.cfa.harvard.edu/viz-bin/VizieR?-source=I/337
[viz-phot-data]: https://vizier.cfa.harvard.edu/viz-bin/VizieR?-source=II/328
[viz-spectro-data]: https://vizier.cfa.harvard.edu/viz-bin/VizieR?-source=III/135A
[viz-cross-data]: https://vizier.cfa.harvard.edu/viz-bin/VizieR?-source=IV/25
[viz-high-data]: https://vizier.cfa.harvard.edu/viz-bin/VizieR?-source=IX/10A
[viz-comb-data]: https://vizier.cfa.harvard.edu/viz-bin/VizieR?-source=V/139
[viz-misc-data]: https://vizier.cfa.harvard.edu/viz-bin/VizieR?-source=VI/135
[viz-non-sto-data]: https://vizier.cfa.harvard.edu/viz-bin/VizieR?-source=VII/233 
[viz-radio-data]: https://vizier.cfa.harvard.edu/viz-bin/VizieR?-source=VIII/65 
