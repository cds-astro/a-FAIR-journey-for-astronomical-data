---
title: "Submitting astronomical data"
teaching: 10
exercises: 2
---

:::::::::::::::::::::::::::::::::::::: questions 

- How and where to submit your data?
- What kind of data can be submitteded (tables, images) ?
- Do and don't when submitting data?
- What are the FAIR principles?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Be aware of the Findable, Accessible, Interoperable and Reusable (FAIR) principles, when preparing your data and its metadata.
- Be aware of how to submit your data in the existing and new Open Science systems,  keeping in mind the Virtual Observatory (VO) standards.

::::::::::::::::::::::::::::::::::::::::::::::::


***Other source: https://cdsarc.cds.unistra.fr/vizier.submit/help.html***

***Other ressource: https://cdsarc.cds.unistra.fr/vizier.submit/publication-notes.html#section5***

***Other: https://vizier.cds.unistra.fr/vizier/submit.htx***



![Data journey from a publication to VizieR: step Submit](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_paths_publish.png){alt="Summary Data journey from a publication to VizieR, step Submit"}


<!--  ----------------------------------------- -->
<!-- 		Submitting 			-->
<!--  ----------------------------------------- -->
<!-- Source: https://cdsarc.cds.unistra.fr/vizier.submit/publication-notes.html#section4 -->
<!-- Source: https://vizier.cds.unistra.fr/vizier/submit.htx // Section 4 -->
## Where to deposit the data?


### Submission form (recommended way)

Since January 2018, the new submission interface is inline.

Some basic checks on the ReadMe and data files are performed. 
It also includes FITS ingestion procedure to improve the discoverability of images and spectra.

***Sentence needed???*** The checking procedure is also available as the anafile package which can be installed with the standard configure and make Linux procedures (man page).

Step-by-step procedure summarizes below.

Link: [https://cdsarc.cds.unistra.fr/vizier.submit/][vizier-submit-login]

Documentation: [doc][vizier-submit-data-help]


### FTP deposit

FTP deposit: see the Publication support page (http://cds.u-strasbg.fr/vizier/submit.htx#ToC4)

Since October 2021, FTP uploads now requires a login authentification.
A web application is available for authors to obtain a temporary login/password:
[https://cds.unistra.fr/ftp/token/][vizier-ftp-login]
(include the FTP instruction).



### Other possibilities

#### Special case: large volumetry

The submission web application is an HTTP service and depends of authors network. The process is dedicated for tables size less than 100Mb but accepts tables until ~200Mb. 

For larger files, please contact the VizieR staff ([cats(at)cdsarc.u-strasbg.fr](mailto:cats@cdsarc.u-strasbg.fr)).


#### Email

E-mail your files to the e-mail address [cats(at)cdsarc.u-strasbg.fr](mailto:cats@cdsarc.u-strasbg.fr) if these are not too bulky (< a few Megabytes).


#### Others

Contact us for other possibilities like download from your site, DVD posting, etc... at: 

Centre de Données astronomiques

11, rue de l'Université

67000 STRASBOURG, France

[cats(at)cdsarc.u-strasbg.fr](mailto:cats@cdsarc.u-strasbg.fr)




<!--  ----------------------------------------- -->
<!--    Fill the Readme description file        -->
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
                - **A***n*      for a character column made of *n* characters;
                - **I***n*      for a column containing an integer number of *n* digits;
                - **F***n.d*    for a column containing a number of width *n* digits and up to *d* digits in the fractional part;
                - **E***n.d*    for a number using the exponential notation;
                - **D***n.d*
        - the [units][vizier-cat-32-units] used in the field; the usage of **SI** units are strongly encouraged, avoid the CGS units (for instance, use **mW/m2** instead of **ergs/s/cm2**).
        - the *label* (heading) of the field, made of a single word (*no embedded blank*); a few [basic conventions][vizier-cat-33-labels] are used for usual parameters (e.g. positions) and related quantities (e.g. mean errors).
        - the *explanations* can start with the following special characters related to some important data characteristics:
                - **\***        (the asterisk)  indicating a [lengthy note][vizier-cat-35-lengthy]
                - **[...]**     (square brackets)       indicating *data ranges*
                - **?** (question mark) indicating a possibility of [blank or NULL][vizier-cat-34-optional] (unspecified) values


- the **References**: section contains the necessary references; the usage of the bibcode(**WARNING: link not found**) is strongly encouraged.

For large sets of references, it is suggested to gather them into a dedicated *reference file* named **refs.dat**.







<!--  ----------------------------------------- -->
<!-- 		Step-by-step: submission form	-->
<!--  ----------------------------------------- -->
<!-- https://cdsarc.cds.unistra.fr/vizier.submit/help.html -->
## Submission form (option 1): step-by-step



<!--  ----------------------------------------- -->
<!-- 		Step-by-step: FTP		-->
<!--  ----------------------------------------- -->
<!-- https://cdsarc.cds.unistra.fr/vizier.submit/help.html -->

## Python + FTP (option 2): step-by-step


### Python cdspyreadme library

Aim: Build ReadMe and MRT builder for authors

Link to Python package: [cdspydreadme][vizier-cdspyreadme]

<iframe src="https://cds-astro.github.io/jupyterlite/lab/index.html" style="border: 1px solid #464646; width: 98%; height:400px" allowfullscreen="" allow="autoplay" data-external="1"></iframe>



### FTP deposit




<!--  ----------------------------------------- -->
<!--            Summary                         -->
<!--  ----------------------------------------- -->

## Summary

<!--
::::::::::::::::::::::::::::::::::::: keypoints
::::::::::::::::::::::::::::::::::::::::::::::::
-->


<!--  ----------------------------------------- -->
<!--            Next Chapters                   -->
<!--  ----------------------------------------- -->
## Next chapters

In the next chapters, you will learn what type of data 



<!--  ----------------------------------------- -->
<!-- 		Link references			-->
<!--  ----------------------------------------- -->
[vizier-ftp-cats]: http://cdsarc.cds.unistra.fr/ftp/cats/
[vizier-readme-std]: https://vizier.cds.unistra.fr/vizier/catstd/catstd-3.1.htx
[vizier-readme-example]: https://cdsarc.cds.unistra.fr/ftp/cats/J/A+A/382/389/ReadMe
[vizier-cdspyreadme]: https://github.com/cds-astro/cds.pyreadme/
<!-- -->
<!-- Not used -->
<!-- -->
[vizier-ftp-login]: https://cds.unistra.fr/ftp/token/
[vizier-publi-data-home]: https://vizier.cds.unistra.fr/vizier/submit.htx
[vizier-publi-notes-help]: https://cdsarc.cds.unistra.fr/vizier.submit/publication-notes.html
[vizier-submit-login]: https://cdsarc.cds.unistra.fr/vizier.submit/index.html
[vizier-submit-data-help]: https://cdsarc.cds.unistra.fr/vizier.submit/help.html
[vizier-submit-old]: http://cdsarc.u-strasbg.fr/viz-bin/Submit
[vizier-cat-2-description]: https://vizier.cds.unistra.fr/vizier/catstd/catstd-2.htx
[vizier-cat-32-units]: https://vizier.cds.unistra.fr/vizier/catstd/catstd-3.2.htx
[vizier-cat-33-labels]: https://vizier.cds.unistra.fr/vizier/catstd/catstd-3.3.htx
[vizier-cat-34-optional]: https://vizier.cds.unistra.fr/vizier/catstd/catstd-3.4.htx
[vizier-cat-35-lengthy]: https://vizier.cds.unistra.fr/vizier/catstd/catstd-3.5.htx
[vizier-fits-validator]: https://cdsarc.cds.unistra.fr/vizier.submit/fitsvalidator.html
[vizier-publi-data-home]: https://vizier.cds.unistra.fr/vizier/submit.htx
[vizier-publi-notes-help]: https://cdsarc.cds.unistra.fr/vizier.submit/publication-notes.html
[vizier-readme-example-aa]: http://cdsarc.u-strasbg.fr/ftp/cats/J/A+A/ReadMe.txt
[vizier-submit-login]: https://cdsarc.cds.unistra.fr/vizier.submit/index.html
[vizier-submit-data-help]: https://cdsarc.cds.unistra.fr/vizier.submit/help.html
[vizier-submit-old]: http://cdsarc.u-strasbg.fr/viz-bin/Submit

