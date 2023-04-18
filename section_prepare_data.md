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




<!--  ----------------------------------------- -->
<!-- 		Submission routes and journals	-->
<!--  ----------------------------------------- -->
## Submission routes and journals


::::::::::::::::::::::::::::::::::::::: discussion

### Details

The submission routes for your data vary depending where you submitted your paper.


![Journals origin in VizieR, data from 2021 (**TO BE UPDATED**)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/journals_origin_on_vizier_from_2021.png){alt="Pie chart: Journals origin in VizieR, data from 2021"}
 

Catalogue per journal: https://vizier.cds.unistra.fr/vizier/welcome/vizierbrowse.gml?designation




:::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::: solution

### Astronomy & Astrophysics Journal (A&A)

By contract with the Journal, the CDS archives the primary data that are published in A&A and puts them at the disposal of the global community.

Once their papers accepted, the **authors submit their MRT files directly** to the CDS.


List of journals included:

- Astronomy & Astrophysics: A&A
- Astronomy & Astrophysics Supplement Series: A&AS


*References* (from the A&A webpage):

- [A&A homepage][aa-home]
- [Publishing tables data to the CDS][aa-publi-data-cds] 
- [Astronomical objects: linking to databases][aa-astro-objects-link]

:::::::::::::::::::::::::



:::::::::::::::: solution

### American Astronomical Society Journals (AAS)

The authors should try to prepare their lenghty tables as machine readable table (MRT) format. 
Then, **VizieR harvests AAS Journal MRTs** and makes these data discoverable and searchable via Virtual Observatory protocols, which is another benefit to using this data format.


List of journals included:

- Astrophysical Journal Letters: AJL
- Astronomical Journal: AJ 
- Astrophysical Journal: ApJ
- Astrophysical Journal Supplement Series: ApJS
- Planeterary Science: Planet. Sci.
- Research notes of the AAS: Res. Notes


*Reference* (from the AAS webpage):

- [AAS homepage][aas-home]
- [Data Guide][aas-data-guide]

:::::::::::::::::::::::::



:::::::::::::::: solution

#### Monthly Notices of the Royal Astronomical Society (MNRAS)

Authors are encouraged to **upload machine-readable versions of their tables on the VizieR database**.
Authors should consult the CDS website for instructions on preparing and submitting tabular data, which include a [template][vizier-readme-example-aa] that can be adapted for MNRAS tables. A hyperlink can be included to CDS from the electronic text of the MNRAS article.


*References* (from the MNRAS webpage):

- [MNRAS homepage][mnras-home]
- [Catalogues and online material][mnras-publi-data-cds] 

:::::::::::::::::::::::::



:::::::::::::::: solution

### Other journals


Examples of other journals included in VizieR:

- Acta Astronomica: AcA
- Astronomische Nachrichten: AN
- Astronomicheskii Zhurnal (Russian): AZh
- Baltic Astronomy: BaltA
- Publications of the Astronomical Society of Japan: PASJ
- Publications of the Astronomical Society of the Pacific: PASP
- Pis'ma v Astronomicheskii Zhurnal (Astronomy Letters): PAZh


:::::::::::::::::::::::::


:::::::::::::::: solution

### Big surveys 

Bigger catalogues are usually **directly retrieved by VizieR**.

Type of big catalogues included:

- Astrometric Data: eg. [Gaia DR1 (Gaia Collaboration, 2016)][viz-astro-data]
- Photometric Data: eg. [AllWISE Data Release (Cutri+ 2013)][viz-phot-data]
- Spectroscopic Data: eg. [Henry Draper Catalogue and Extension (Cannon+ 1918-1924; ADC 1989)][viz-spectro-data]
- Cross-Identifications: eg. [HD identifications for Tycho-2 stars (Fabricius+, 2002)][viz-cross-data] 
- High-Energy data: eg. [ROSAT All-Sky Bright Source Catalogue (1RXS) (Voges+ 1999)][viz-high-data]
- Combined data: eg. [The SDSS Photometric Catalog, Release 9 (Adelman-McCarthy+, 2012)][viz-comb-data]
- Miscellaneous: eg. [All-sky spectrally matched Tycho2 stars (Pickles+, 2010)][viz-misc-data]
- Non-stellar Objects: eg. [The 2MASS Extended sources (IPAC/UMass, 2003-2006)][viz-non-sto-data]
- Radio and Far-IR data: eg. [1.4GHz NRAO VLA Sky Survey (NVSS) (Condon+ 1998)][viz-radio-data]
  

<!--

SELECT TOP 5 name, popu FROM METAcat
WHERE name LIKE 'V/%'
ORDER BY popu DESC;

==> http://tapvizier.cds.unistra.fr/adql/
-->

:::::::::::::::::::::::::



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
