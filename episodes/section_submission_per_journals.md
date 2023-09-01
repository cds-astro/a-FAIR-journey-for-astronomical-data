---
title: "Submission routes and journals"
teaching: 3
exercises: 0
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

Interactive window: VizieR catalogues provenance per journal.
<iframe src="https://manonmarchand.github.io/vizier-stats/" style="border: none; width: 98%; height:500px" allowfullscreen="" allow="autoplay" data-external="1"></iframe>

Link: [Catalogues and files available at CDS][vizier-cat-per-journal]



<!--  ----------------------------------------- -->
<!-- 		AAS				-->
<!--  ----------------------------------------- -->
## American Astronomical Society Journals (AAS)

The CDS selects tables from published papers which will be ingested in VizieR.
<!-- tables coming from AAS are not systematically ingested in VizieR. -->
Machine readable tables (MRT) are prioritised, but other tables or FITS spectra/images can also be added.

List of journals included:

- The Astrophysical Journal: ApJ
- The Astronomical Journal: AJ 
- The Astrophysical Journal Supplement Series: ApJS
- The Astrophysical Journal Letters: ApJL


<!-- To select ApJ and not ApJL .... => 
SELECT count(bibcode) FROM METAcat
WHERE catid>1
AND bibcode LIKE '%ApJ.%'
AND bibcode NOT LIKE '%ApJ.%L.%';
-->


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

Before publication, A&A editors and CDS decide which data to ingest in VizieR. 
The authors then need to submit the requested data to CDS.
Other tables already published can also be selected by the CDS.


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

CDS selection or direct authors submission depending on CDS acceptation.

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


Examples of other journals included in VizieR, ordered by their percentage of catalogues ingested in VizieR:

- Publications of the Astronomical Society of the Pacific: PASP (0.85%)
- Pis'ma v Astronomicheskii Zhurnal: PAZh / AstL (0.73%)
- Astronomicheskii Zhurnal: AZh (0.66%)
- Acta Astronomica: AcA (0.58%)
- Publications of the Astronomical Society of Japan: PASJ (0.41%)
- Astronomische Nachrichten: AN (0.30%)
- Baltic Astronomy: BaltA (0.23%)
- Nature: Natur (0.10%) <!-- 25-->
- The Planetary Science Journal: Sci (0.08%)
- Research notes of the AAS: RNAAS (0.008%) <!-- 2 catalogues -->

<!-- 
SELECT name, bibcode FROM METAcat
WHERE catid>1
AND bibcode NOT LIKE '%ApJ.%'
AND bibcode NOT LIKE '%ApJ.%L.%'
AND bibcode NOT LIKE '%AJ.%'
AND bibcode NOT LIKE '%ApJS.%'
AND bibcode NOT LIKE '%A&A.%'
AND bibcode NOT LIKE '%A&AS.%' 
AND bibcode NOT LIKE '%MNRAS.%'
AND bibcode NOT LIKE '%PASP.%'
AND bibcode NOT LIKE '%PAZh.%' 
AND bibcode NOT LIKE '%AstL.%'
AND bibcode NOT LIKE '%AZh.%'
AND bibcode NOT LIKE '%AcA.%'
AND bibcode NOT LIKE '%PASJ.%'  
AND bibcode NOT LIKE '%AN.%'
AND bibcode NOT LIKE '%BaltA.%'
AND bibcode NOT LIKE '%Natur.%'
AND bibcode NOT LIKE '%Sci.%'  
AND bibcode NOT LIKE '%RNAAS.%';

==> http://tapvizier.cds.unistra.fr/adql/

-->


<!--  ----------------------------------------- -->
<!-- 		Big surveys			-->
<!--  ----------------------------------------- -->
## Large datasets / surveys 

Very large catalogues are usually **directly retrieved by VizieR** (from ESA, ESO, NASA, Stsci, …), after selection by CDS astronomers.

Note that the CDS is **not a mirror**, and a selection on the columns can be done.

Type of big catalogues included (as listed on the [VizieR hierarchical organisation webpage][vizier-cat-per-journal]):

| Category | Type of data  | Example of VizieR catalogue| Description 							|
| - | --- 	   | ---- 			| ------ 							|
| I 	| Astrometric Data | [I/355][viz-astro-data] 	| Gaia DR3 Part 1. Main source (Gaia collaboration, 2022)	|
| II 	| Photometric Data | [II/328][viz-phot-data] 	| AllWISE Data Release (Cutri+, 2013)	|
| III 	| Spectroscopic Data | [III/283][viz-spectro-data] 	| RAVE 6th data release (Steinmetz+, 2020)	|
| IV 	| Cross-Identifications | [IV/39][viz-cross-data] 	| TESS Input Catalog version 8.2 (TIC v8.2) (Paegert+, 2021)		|
| V 	| Combined Data | [V/154][viz-comb-data] 	| Sloan Digital Sky Surveys (SDSS), Release 16 (DR16) (Ahumada+, 2020)		|
| VI 	| Miscellaneous | [VI/135][viz-misc-data] 	| All-sky spectrally matched Tycho2 stars (Pickles+, 2010) 	|
| VII 	| Non-stellar Objects | [VII/233][viz-non-sto-data] 	| The 2MASS Extended sources (IPAC/UMass, 2003-2006) 	|
| VIII 	| Radio and Far-IR data | [VIII/65][viz-radio-data] 	| 1.4GHz NRAO VLA Sky Survey (NVSS) (Condon+, 1998)	|
| IX 	| High-Energy Data | [IX/68][viz-high-data] 	| XMM-Newton Serendipitous Source Catalogue 4XMM-DR12 (Webb+, 2023) 	|


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

- Initiated by authors / editors
- Initiated by the CDS

To face an increasing volume and according to the CDS mission, VizieR selects the articles to be processed.

- Main journals origin : AAS (ApJ, AJ, ApJS, ApJL), A&A, MNRAS
- Authors asking for VizieR publication
- Scientific criteria such as the origin of the measurements
(e.g. observations have a higher priority than models)
- Effort required to make the data reusable (preferably MRT) is taken into account in the selection
- Special case : A&A editors request authors to submit their data in CDS

::::::::::::::::::::::::::::::::::::::::::::::::


<!--  ----------------------------------------- -->
<!--            Next Chapters                   -->
<!--  ----------------------------------------- -->
## Next chapters

In the next chapters, you will learn how to prepare and submit your data to VizieR step-by-step, and then you will follow the journey of your data in the Virtual Observatory and up to EOSC. 



<!--  ----------------------------------------- -->
<!-- 		Link references			-->
<!--	==> See links.md file			-->
<!--  ----------------------------------------- -->
