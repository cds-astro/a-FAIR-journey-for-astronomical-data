---
title: "Submission routes and journals"
teaching: 10
exercises: 2
---

:::::::::::::::::::::::::::::::::::::: questions 

- Which submission route to follow?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Be aware of  x x x

::::::::::::::::::::::::::::::::::::::::::::::::



<!--  ----------------------------------------- -->
<!-- 	Intro 					-->
<!--  ----------------------------------------- -->
## Overview

The submission routes for your data vary depending where you submitted your paper.

2 types of VizieR workflows:

- Initiated by authors
- Initiated by the CDS


![Journals origin in VizieR, data from 2021 (**TO BE UPDATED**)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/journals_origin_on_vizier_from_2021.png){alt="Pie chart: Journals origin in VizieR, data from 2021"}
 

Catalogue per journal: https://vizier.cds.unistra.fr/vizier/welcome/vizierbrowse.gml?designation


### Priorities and selection management for authors publication

To face an increasing volume and according to the CDS mission, VizieR selects the articles to be processed.

- Journals origin : AAS (AJ, ApJ, ApJS), A&A, MNRAS
- Authors asking for VizieR publication
- Scientific criteria such as the origin of the measurements
(e.g. observations have a higher priority than models)
- Effort required to make the data reusable (e.g. MRT) is taken into account in the selection of AAS journals
(ApJ, ApJS and AJ).
- Special case : A&A editors request authors to submit their data in CDS.



<!--  ----------------------------------------- -->
<!-- 		A&A				-->
<!--  ----------------------------------------- -->
## Astronomy & Astrophysics Journal (A&A)

By contract with the Journal, the CDS archives the primary data that are published in A&A and puts them at the disposal of the global community.

Once their papers accepted, the **authors submit their MRT files directly** to the CDS.


List of journals included:

- Astronomy & Astrophysics: A&A
- Astronomy & Astrophysics Supplement Series: A&AS


*References* (from the A&A webpage):

- [A&A homepage][aa-home]
- [Publishing tables data to the CDS][aa-publi-data-cds] 
- [Astronomical objects: linking to databases][aa-astro-objects-link]



<!--  ----------------------------------------- -->
<!-- 		AAS				-->
<!--  ----------------------------------------- -->
## American Astronomical Society Journals (AAS)

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





<!--  ----------------------------------------- -->
<!-- 		MNRAS				-->
<!--  ----------------------------------------- -->
## Monthly Notices of the Royal Astronomical Society (MNRAS)

Authors are encouraged to **upload machine-readable versions of their tables on the VizieR database**.
Authors should consult the CDS website for instructions on preparing and submitting tabular data, which include a [template][vizier-readme-example-aa] that can be adapted for MNRAS tables. A hyperlink can be included to CDS from the electronic text of the MNRAS article.


*References* (from the MNRAS webpage):

- [MNRAS homepage][mnras-home]
- [Catalogues and online material][mnras-publi-data-cds] 



<!--  ----------------------------------------- -->
<!-- 		Other journals			-->
<!--  ----------------------------------------- -->
## Other journals


Examples of other journals included in VizieR:

- Acta Astronomica: AcA
- Astronomische Nachrichten: AN
- Astronomicheskii Zhurnal (Russian): AZh
- Baltic Astronomy: BaltA
- Publications of the Astronomical Society of Japan: PASJ
- Publications of the Astronomical Society of the Pacific: PASP
- Pis'ma v Astronomicheskii Zhurnal (Astronomy Letters): PAZh



<!--  ----------------------------------------- -->
<!-- 		Big surveys			-->
<!--  ----------------------------------------- -->
## Large datasets / surveys 

Bigger catalogues are usually **directly retrieved by VizieR** (from ESA, ESO, NASA, Stsci, …), after selection by CDS astronomers.

Note that the CDS is **not a mirror**, and a selection on the columns is done.

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
