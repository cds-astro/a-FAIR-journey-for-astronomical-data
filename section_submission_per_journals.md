---
title: "Submission routes and journals"
teaching: 10
exercises: 2
---

:::::::::::::::::::::::::::::::::::::: questions 

- What to do with my data knowing my journal?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Be aware of the different submission routes

::::::::::::::::::::::::::::::::::::::::::::::::


<!--  ----------------------------------------- -->
<!-- 	Intro 					-->
<!--  ----------------------------------------- -->
## Overview

The submission routes for your data vary depending where you submitted your paper.

2 types of VizieR workflows:

- Initiated by authors
- Initiated by the CDS

<iframe src="https://manonmarchand.github.io/vizier-stats/" style="border: none; width: 98%; height:500px" allowfullscreen="" allow="autoplay" data-external="1"></iframe>

Link: [Catalogues and files available at CDS][vizier-cat-per-journal]



<!--  ----------------------------------------- -->
<!-- 		AAS				-->
<!--  ----------------------------------------- -->
## American Astronomical Society Journals (AAS)

The CDS selects tables which will be ingested in VizieR.
<!-- tables coming from AAS are not systematically ingested in VizieR. -->
Machine readable tables (MRT) are prioritised, but other tables or FITS spectra/images can also be added.

List of journals included:

- The Astrophysical Journal Letters: ApJL
- The Astronomical Journal: AJ 
- The Astrophysical Journal: ApJ
- The Astrophysical Journal Supplement Series: ApJS
- The Planetary Science Journal: Planet. Sci.
- Research notes of the AAS: Res. Notes


------------------

*Recommendations* (from the AAS webpage):

The authors should try to prepare their lenghty tables as machine readable table (MRT) format. 
Then, **VizieR harvests AAS Journal MRTs** and makes these data discoverable and searchable via Virtual Observatory protocols, which is another benefit to using this data format.


*Reference* (from the AAS webpage):

- [AAS homepage][aas-home]
- [Data Guide][aas-data-guide]




<!--  ----------------------------------------- -->
<!-- 		A&A				-->
<!--  ----------------------------------------- -->
## Astronomy & Astrophysics Journal (A&A)

The editor decides the data to ingest in VizieR. 
The authors have to submit their data in CDS.


List of journals included:

- Astronomy & Astrophysics: A&A
- Astronomy & Astrophysics Supplement Series: A&AS


------------------

*Recommendations* (from the A&A webpage):

By contract with the Journal, the CDS archives the primary data that are published in A&A and puts them at the disposal of the global community.

Once their papers accepted, the **authors submit their MRT files directly** to the CDS.


*References* (from the A&A webpage):

- [A&A homepage][aa-home]
- [Publishing tables data to the CDS][aa-publi-data-cds] 
- [Astronomical objects: linking to databases][aa-astro-objects-link]




<!--  ----------------------------------------- -->
<!-- 		MNRAS				-->
<!--  ----------------------------------------- -->
## Monthly Notices of the Royal Astronomical Society (MNRAS)

CDS selection or authors submission for CDS acceptation.

------------------

*Recommendations* (from the MNRAS webpage):

Authors are encouraged to **upload machine-readable versions of their tables on the VizieR database**.
Authors should consult the CDS website for instructions on preparing and submitting tabular data, which include a [template][mnras-vizier-readme-example-aa] that can be adapted for MNRAS tables. A hyperlink can be included to CDS from the electronic text of the MNRAS article.


*References* (from the MNRAS webpage):

- [MNRAS homepage][mnras-home]
- [Catalogues and online material][mnras-publi-data-cds] 



<!--  ----------------------------------------- -->
<!-- 		Other journals			-->
<!--  ----------------------------------------- -->
## Other journals

Any other journals needs the author to submit the data.


Examples of other journals included in VizieR (and percentage of catalogues ingested in VizieR):

- Publications of the Astronomical Society of the Pacific: PASP (2.7%)
- Pis'ma v Astronomicheskii Zhurnal: PAZh (2.2%)
- Astronomicheskii Zhurnal: AZh (2.1%)
- Acta Astronomica: AcA (1.6%)
- Publications of the Astronomical Society of Japan: PASJ (1.3%)
- Astronomische Nachrichten: AN (0.95%)
- Baltic Astronomy: BaltA (0.7%)



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
<!--            Summary                         -->
<!--  ----------------------------------------- -->
<!-- Source: AAS presentation Gilles 2021 -->
## Summary: Submission per journal

::::::::::::::::::::::::::::::::::::: keypoints

2 types of VizieR workflows:

- Initiated by authors
- Initiated by the CDS

To face an increasing volume and according to the CDS mission, VizieR selects the articles to be processed. (**TRUE -- AG??**)

- Main journals origin : AAS (AJ, ApJ, ApJS), A&A, MNRAS
- Authors asking for VizieR publication
- Scientific criteria such as the origin of the measurements
(e.g. observations have a higher priority than models)
- Effort required to make the data reusable (e.g. MRT) is taken into account in the selection of AAS journals
- Special case : A&A editors request authors to submit their data in CDS

::::::::::::::::::::::::::::::::::::::::::::::::


<!--  ----------------------------------------- -->
<!--            Next Chapters                   -->
<!--  ----------------------------------------- -->
## Next chapters

In the next chapters, you will learn how to submit your data to VizieR step-by-step, and then you will follow the journey of your data in the Virtual Observatory and up to EOSC. 



<!--  ----------------------------------------- -->
<!-- 		Link references			-->
<!--	==> See links.md file			-->
<!--  ----------------------------------------- -->
