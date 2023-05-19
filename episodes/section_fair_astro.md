---
title: "FAIR principles for astronomical data"
teaching: 10
exercises: 2
---

:::::::::::::::::::::::::::::::::::::: questions 

- What are the FAIR principles?
- What does it mean for astronomical data?
- Do and don't when publishing data?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Be aware of the Findable, Accessible, Interoperable and Reusable (FAIR) principles, when preparing your data and its metadata.

::::::::::::::::::::::::::::::::::::::::::::::::

![Data journey from a publication to VizieR: step Prepare (part 1)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_paths_prepare_part1.png){alt="Summary Data journey from a publication to VizieR, step Prepare, part 1"}



<!--  ----------------------------------------- -->
<!--            Overview                        -->
<!--  ----------------------------------------- -->
<!-- Source: https://vizier.cds.unistra.fr/vizier/submit.htx -->
## Overview

The CDS and other astronomical data centers are storing and distributing the astronomical data to promote their usage primarily by professional astronomers.

In order to ensure the scientific quality of the data, we therefore require that the data are related to a publication in a refereed journal, either as tables or catalogues actually published, or as a paper describing the data and their context. 

Furthermore, the data should be *described* accurately enough to allow an unambiguous interpretation of the data, and faciliate their usability. 

In this course, we will review in this course the best practices for data publication in the astronomical field.


<!--
For a quick view of the guidelines and recommandations for publishing your data at CDS, please have a look at the ["Make your data visible" brochure][vizier-make-your-data-visible].

See also the Best Practices for Data Publication in the Astronomical Literature (T.Chen, 2022). The article is dedicated for authors, and is a basis of good practices expected in journals and data-centers.

In order to facilitate the usability of the data, and to allow their processing by the data centers, we at CDS require that:

- the data are *described* accurately enough to allow an unambiguous interpretation of the data, as well as a comprehension of the context in which the data were acquired and/or processed; a single ascii file, named *ReadMe*, is designed for this role.
- the data are in a format which allows their usage by tools currently in usage in our discipline - normally *flat ascii files*; other formats can be accepted, but are converted into flat files.


The present course just tries to answer to some frequently asked question about how to prepare the data for their inclusion in the Data Center documents. 

A full description of the standard conventions used for the documentation of the catalogues is available from [there][vizier-standard-convention].

-->


<!--  ----------------------------------------- -->
<!-- 		Introduction 			-->
<!--  ----------------------------------------- -->
## What are the FAIR principles?

Formalized by Wilkinson et al. in 2016 ([10.1038/sdata.2016.18][wilkinson_2016]), the FAIR Guiding Principles have emerged over the last few years. The underlying idea is to provide a set of guidelines (neither a standard not a specification) for making research data in a broad sense (not only data, but also algorithms, tools, and workﬂows that led to that data) **F**indable, **A**ccessible, **I**nteroperable and **R**eusable, ultimately ensuring standardised machine actionability. 

Many great courses can be found online explaining those principles in more details.
In this course, we will summarize them and focus more on what it means for astronomical data. 
 
![FAIR guiding principles for data resources](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/fair_principles.png){alt="Findable Accessible Interoperable Reusable principes"}
*Credit: Open Science Training Handbook, CC0 1.0 Universal, https://doi.org/10.5281/zenodo.1212496*



::::::::::::::::::::::::::::::::::::::: discussion

### Details

The FAIR Guiding Principles for scientiﬁc data management and stewardship as outlined by M. Wilkinson et al. (2016). 

:::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::: solution

### To be Findable

The first step before reusing the data is to be able to find them. 
The metadata and data should be easy to find for both humans and computers. 

F1. (Meta)data are assigned a globally unique and persistent identiﬁer

F2. Data are described with rich metadata (deﬁned by R1 below)

F3. Metadata clearly and explicitly include the identiﬁer of the data it describes

F4. (Meta)data are registered or indexed in a searchable resource



:::::::::::::::::::::::::


:::::::::::::::: solution

### To be Accessible

Once the data can be found, the user needs to know how to access them. That could include authentification and authorisation.
The accessibility of the data does not mean that they are open!

The data should be 'as open as possible, as closed as necessary', following the H2020 Program Guidelines on FAIR Data.


A1. (Meta)data are retrievable by their identiﬁer using a standardized communications protocol

- A1.1 The protocol is open, free, and universally implementable
- A1.2 The protocol allows for an authentication and authorization procedure, where necessary

A2. Metadata are accessible, even when the data are no longer available




:::::::::::::::::::::::::


:::::::::::::::: solution

### To be Interopable

Those data can then be combined with different datasets, and interoperate with other applications or workflows for analysis, storage, and processing, thanks to rich metadata.


I1. (Meta)data use a formal, accessible, shared, and broadly applicable language for knowledge representation.

I2. (Meta)data use vocabularies that follow FAIR principles

I3. (Meta)data include qualiﬁed references to other (meta)data


:::::::::::::::::::::::::


:::::::::::::::: solution

### To be Reusable

The ultimate goal of FAIR is to optimise the reuse of data. To achieve this, metadata and data should be well-described, including a clear and accessible license.
It should be clear how the data can and cannot be reused, remixed or redistributed.


R1. Meta(data) are richly described with a plurality of accurate and relevant attributes

- R1.1. (Meta)data are released with a clear and accessible data usage license
- R1.2. (Meta)data are associated with detailed provenance
- R1.3. (Meta)data meet domain-relevant community standards

:::::::::::::::::::::::::




<!--  ----------------------------------------- -->
<!-- 		Best Practices (Chen+22)	-->
<!--  ----------------------------------------- -->
## Best Practices for Data Publication in the Astronomical Literature

In 2022, Chen et al. ([10.3847/1538-4365/ac6268][Chen_2022]) published a set of guidelines summarizing the best practices for publishing data in astronomy and astrophysics journals. 

Everyone is encouraged to read their paper. For the sake of this course, only their *Checklist of Recommendations for Publishing Data in the Literature* (Appendix A of their paper) is included below.

These recommendations are intended for authors, referees, and science editors to consult in order to avoid various pit-falls that often impede the interpretation of data and metadata by readers, and parsing by software, and therefore also complicate and delay integration of the data into astronomical databases.



<!--  ----------------------------------------- -->
----------
### General rules (§2)

(a) Define all symbols, acronyms, and abbreviations at first use.
(b) Provide uncertainty and confidence level when reporting a new measurement.
(c) Present the appropriate number of significant figures for numerical measurements and uncertainties that
match the precision of the measurements.
(d) Report the units for measurements if present, and adopt commonly-used ones.
(e) Indicate preferred values if applicable.


#### Examples
```output
[a] “... used by the Dark Energy Survey (DES)...”
[b] The period of a periodic phenomenon should be given as “P = 1.23456±0.00012 days” instead of “P = 1.23456(12) days”. 
[c] Present a measurement as 0.123±0.002, not 0.12345±0.002 or 0.123±0.00234.
[d] Present source color “(B-V) = 0.45 mag” instead of “(B-V) = 0.45”
[e] State your preferred solution in the text and indicated in bold in your Table: example from [Grieves et al. (2021)][Grieves_2021]
```

![Extract from Table 4 from Grieves et al. (2021)](file:///home/agonneau/Programs/Github/a-FAIR-journey-for-astronomical-data/episodes/images/grieves_2012_table4_short.png){alt="Small extract of Table 4 from Grieves et al. 2021, showing the usage of bold to indicate their preferred solution when providing multiple options for stellar parameters"}

 
<!--  ----------------------------------------- -->
----------
### Nomenclature (§2.1)

(a) Provide the complete name for each object. (§2.1.1)
(b) Include the “J” in names based on J2000 coordinates. (§2.1.1)
(c) Insert spacers between a catalog name and the identifiers within the catalog. (§2.1.1)
(d) Distinguish between part of an object and the object itself. (§2.1.1)
(e) Do not use the same name for different objects. (§2.1.1)
(f) Always assign a name and verify the name is unique. (§2.1.2)
(g) Keep the appropriate number of significant figures in coordinate-based names. (§2.1.2)
(h) Use established names for known objects and check for the correct formatting. (§2.1.3)
(i) Confirm the names and positions for cross-identifications. (§2.1.4)
(j) Cross-match the same objects in different tables within the same article. (§2.1.4)


#### Examples
```output

## IAU conventions
[a] **Include table 1 as an exercice?**
[b] Use “BR J0529-3526” instead of “BR0529-3526”.
[c] Use B3 2327+391, not B32327+391.
[d] Use “3C 295 cluster” instead of “3C 295” when referring to the cluster.
[e] The tau Ceti system now has four planets: e, f, g, and h. Since tau Ceti b, c, and d were refuted,
the letter designations b, c, and d were not reused for the newer planets to avoid confusion.

## New objects
[f] Confirm any new acronym to the [IAU Dictionary of Nomenclature of Celestial Objects][iau-dico-nomenclature]
[g] J092712.64+294344.0 indicates a positional accuracy of 0.15 arcsec while J092712.644+294344.02 indicates an accuracy of 0.015 arcsec.

## Known objects
[h] Creating a fanciful name for an object with an existing designation is especially discourage.
[i] Validate all the identifiers for known objects in their publications through [Sesame][sesame-cds] a service hosted by CDS that queries NED, SIMBAD, and VizieR to help resolve object names.


## Cross-identifications
[i] Always verify with established databases that all of the names given to an object are valid cross-identifications for the object and that the listed positions are for the same object.
[j] Table 4 of Kundu et al. (2007) provided for the same objects both their X-ray identification number as given in Table 2 and optical identification number as in Table 3 of the article, and therefore linked the position and photometry data for the objects discussed in all three tables.

```


<!--  ----------------------------------------- -->
----------
### Astrometry (§2.2)

(a) Provide the best available coordinates.
(b) Specify the celestial reference system and/or frame.
(c) Indicate the equinox and epoch of observation when necessary.
(d) State the wavelength range from which astrometry is obtained.

#### Examples
```output
[a] i
```

----------


<!--  ----------------------------------------- -->
### Photometry (§2.3)

(a) State the facility, telescope and instrument used.
(b) Describe the method used to estimate photometry.
(c) Use standard passband/filter identifiers.
(d) Clarify the magnitude system.
(e) Specify spectral transitions completely.

#### Examples
```output
[a] i
```


----------


<!--  ----------------------------------------- -->
### Time (§2.4)

(a) Provide the time of observation and exposure time.
(b) Favor full Julian Dates over abbreviated or offset Julian Dates.
(c) Include phase timing measures along with reported periods when relevant.
(d) State when observations from multiple missions are executed simultaneously.

#### Examples
```output
[a] i
```

----------


<!--  ----------------------------------------- -->
### Redshift/velocity (§2.5)

(a) Describe the method of redshift measurements (spectroscopic, photometric, etc.) and give references to the
model/method.
(b) Specify the reference frame of the redshift measurements (barycentric, heliocentric, galactocentric, etc.).
(c) Provide the frequency/wavelength from which the measurement is obtained.
(d) State whether a published recessional velocity is based on observed frequency or wavelength shifts (i.e.,
radio or optical convention).
(e) Indicate the quality of the measurement when possible.

#### Examples
```output
[a] i
```


----------


<!--  ----------------------------------------- -->
### Classifications (§2.6)

(a) Utilize established classifications as available.
(b) Define new classifications clearly.

#### Examples
```output
[a] i
```

----------



<!--  ----------------------------------------- -->
### Orbital parameters (§2.7)

(a) Avoid using “longitude of periapsis” in place of “argument of periapsis”.
(b) Be explicit about which body’s orbit a longitude or argument of periapsis refers to (e.g., planet or host
star).
(c) Include time of periapsis as appropriate.

#### Examples
```output
[a] i
```


----------


<!--  ----------------------------------------- -->
### Tables (§3.1)

(a) Provide a clear title and unambiguous labels for columns.
(b) Explain the content of each column, including symbols and flags.
(c) Keep each column homogeneous.
(d) Use the same explicitly defined non-numeric representations for missing (null) values throughout.
(e) Prepare ReadMe files for machine-readable tables.

#### Examples
```output
[a] i
```

----------



<!--  ----------------------------------------- -->
### Figures (§3.2)

(a) Provide clear caption, legend and axis labels for each figure.
(b) Design the graphics to be accessible.
(c) Make “data behind the plots” publicly available.

#### Examples
```output
[a] i
```

----------



<!--  ----------------------------------------- -->
### Data archiving and access (§4)

(a) Append small data sets as part of the publication.
(b) Deposit large or complex data at a long-term archive most appropriate for your data. Adhere to the specific
format requirements from the archives.
(c) Provide a complete list of metadata.
(d) Include a Data Availability Statement if required by the journal.
(e) Do not publish data sets at URLs lacking long-term support.

#### Examples
```output
[a] i
```

----------



<!--  ----------------------------------------- -->
### Literature citations (§5.1)

(a) Cite the original references.
(b) Use preferred citations by the authors.
(c) Provide full provenance of the data. Credit the originator of archival data, including the Principal Investi-
gator.
(d) Include all references in the bibliography section.
(e) Distinguish original data in your article and data taken from other work.


#### Examples
```output
[a] i
```

----------



<!--  ----------------------------------------- -->
### Facility credits (§5.2)

(a) Indicate the facilities involved, such as telescopes, instruments, and databases.
(b) Use standard keywords when possible.
(c) Include facility’s own statement if available.

#### Examples
```output
[a] i
```


----------


<!--  ----------------------------------------- -->
### Software credits (§5.3)

(a) List the software and version used in the production of the article.

#### Examples
```output
[a] i
```

----------


<!--  ----------------------------------------- -->
### Digital object identifiers - DOI (§5.4)

(a) Use DOIs to cite data sets, software and services if available.

#### Examples
```output
[a] i
```

----------


<!--  ----------------------------------------- -->
### Data content keywords (§6)

(a) Tag articles with relevant data content keywords from the UAT ([Unified Astronomy Thesaurus][uat]).

#### Examples
```output
[a] i
```


<!--  ----------------------------------------- -->
<!-- 		Keypoints 			-->
<!--  ----------------------------------------- -->
## Small tips for FAIR data: summary

::::::::::::::::::::::::::::::::::::: keypoints

- For tables containing known astronomical objects, an existing **non-altered** name must be given along with the coordinates.
- All columns must be explained with **their corresponding unit**.
- Your columns should be homogeneous, and you should avoid mixing measurements with different meanings: errors mixed with limts, or values with different units (that should be in different columns).
- When there is more than one table, the objects in common must be identified with the **same name between tables**.

::::::::::::::::::::::::::::::::::::::::::::::::


Catalogues require an article reference from a refereed journal

Make sure that your data are reusable:

- Give **non-alterned names** and **coordinates** for astronomical objects
- Give the **units** and stick to **one same unit per column** in a table
- Keep the **same identifiers between tables** for the same astronomical object!


Important point: Tables of astronomical objects without coordinates cannot be added into the SIMBAD database.



<!--  ----------------------------------------- -->
<!-- 		Case study 			-->
<!--  ----------------------------------------- -->
## Case study

- Fix "bad examples"??



<!--  ----------------------------------------- -->
<!--            Next Chapters                   -->
<!--  ----------------------------------------- -->
## Next chapters

In the next chapters, you will learn how to prepare your data before submitting them to VizieR, and ultimately how to search your data using the EOSC tools.



<!--  ----------------------------------------- -->
<!-- 		Link references			-->
<!--  ----------------------------------------- -->
[wilkinson_2016]: https://ui.adsabs.harvard.edu/link_gateway/2016NatSD...360018W/doi:10.1038/sdata.2016.18
[Chen_2022]: https://iopscience.iop.org/article/10.3847/1538-4365/ac6268
[Grieves_2021]: http://doi.org/10.1051/0004-6361/202039586
[uat]: https://astrothesaurus.org/
[iau-dico-nomenclature]: http://vizier.u-strasbg.fr/cgi-bin/Dic
<!-- -->
[vizier-publi-data-home]: https://vizier.cds.unistra.fr/vizier/submit.htx
[vizier-publi-notes-help]: https://cdsarc.cds.unistra.fr/vizier.submit/publication-notes.html
[vizier-submit-data-help]: https://cdsarc.cds.unistra.fr/vizier.submit/help.html
[sesame-cds]: https://cds.unistra.fr/cgi-bin/Sesame
<!-- -->
<!-- Not used -->
<!-- -->
[vizier-make-your-data-visible]: https://vizier.cds.unistra.fr/vizier/submit/Make_your_data_visible.pdf


<!--  ----------------------------------------- -->
<!-- 		Glossary			-->
<!--  ----------------------------------------- -->
<!-- 
DOI—Digital Object Identiﬁer; a code used to permanently and stably identify (usually digital) objects. DOIs provide a standard mechanism for retrieval of
metadata about the object, and generally a means to access the data object itself.
FAIR—Findable, Accessible, Interoperable, Reusable
-->

