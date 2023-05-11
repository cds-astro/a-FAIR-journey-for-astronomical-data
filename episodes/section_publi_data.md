---
title: "Publishing astronomical data"
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


***Other source: https://cdsarc.cds.unistra.fr/vizier.submit/help.html***

***Other ressource: https://cdsarc.cds.unistra.fr/vizier.submit/publication-notes.html#section5***

***Other: https://vizier.cds.unistra.fr/vizier/submit.htx***



![Data journey from a publication to VizieR: step Publish](file:///home/agonneau/Programs/Github/a-FAIR-journey-for-astronomical-data/episodes/images/vizier_paths_publish.png){alt="Summary Data journey from a publication to VizieR, step Publish"}


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
<!-- 		Step-by-step: submission form	-->
<!--  ----------------------------------------- -->
<!-- https://cdsarc.cds.unistra.fr/vizier.submit/help.html -->
## Step-by-step: Submission form



<!--  ----------------------------------------- -->
<!-- 		Step-by-step: FTP		-->
<!--  ----------------------------------------- -->
<!-- https://cdsarc.cds.unistra.fr/vizier.submit/help.html -->

## Step-by-step: Python + FTP


## Python cdspyreadme library

Aim: Build ReadMe and MRT builder for authors

Link to Python package: [cdspydreadme][vizier-cdspyreadme]

<iframe src="https://cds-astro.github.io/jupyterlite/lab/index.html" style="border: 1px solid #464646; width: 98%; height:400px" allowfullscreen="" allow="autoplay" data-external="1"></iframe>



## FTP deposit





## Summary



<!--  ----------------------------------------- -->
<!--            Next Chapters                   -->
<!--  ----------------------------------------- -->
## Next chapters

In the next chapters, you will learn what type of data 



<!--  ----------------------------------------- -->
<!-- 		Link references			-->
<!--  ----------------------------------------- -->
[vizier-cdspyreadme]: https://github.com/cds-astro/cds.pyreadme/
[vizier-ftp-login]: https://cds.unistra.fr/ftp/token/
[vizier-publi-data-home]: https://vizier.cds.unistra.fr/vizier/submit.htx
[vizier-publi-notes-help]: https://cdsarc.cds.unistra.fr/vizier.submit/publication-notes.html
[vizier-submit-login]: https://cdsarc.cds.unistra.fr/vizier.submit/index.html
[vizier-submit-data-help]: https://cdsarc.cds.unistra.fr/vizier.submit/help.html
[vizier-submit-old]: http://cdsarc.u-strasbg.fr/viz-bin/Submit
