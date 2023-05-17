---
title: "FAIR principles for astronomical data"
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

::::::::::::::::::::::::::::::::::::::::::::::::

![Data journey from a publication to VizieR: step Prepare (part 1)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_paths_prepare_part1.png){alt="Summary Data journey from a publication to VizieR, step Prepare, part 1"}



<!--  ----------------------------------------- -->
<!--            Overview                        -->
<!--  ----------------------------------------- -->
<!-- Source: https://vizier.cds.unistra.fr/vizier/submit.htx -->
## Overview

The CDS and other astronomical data centers are storing and distributing the astronomical data to promote their usage primarily by professional astronomers.

In order to ensure the scientific quality of the data, we therefore require that the data are related to a publication in a refereed journal, either as tables or catalogues actually published, or as a paper describing the data and their context. 

Before detailing how to prepare the data for their inclusion into VizieR, we will review in this course the best practices for data publication in the astronomical field.

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


A1. (Meta)data are retrievable by their identiﬁer using a standardized communications protocol

A1.1 The protocol is open, free, and universally implementable

A1.2 The protocol allows for an authentication and authorization procedure, where necessary

A2. Metadata are accessible, even when the data are no longer available




:::::::::::::::::::::::::


:::::::::::::::: solution

### To be Interopable

**I**nteroperable use of the data with other data
// The data usually need to be integrated with other data. In addition, the data need to interoperate with applications or workflows for analysis, storage, and processing.


I1. (Meta)data use a formal, accessible, shared, and broadly applicable language for knowledge representation.

I2. (Meta)data use vocabularies that follow FAIR principles

I3. (Meta)data include qualiﬁed references to other (meta)data


:::::::::::::::::::::::::


:::::::::::::::: solution

### To be Reusable

**R**e-use the data

// The ultimate goal of FAIR is to optimise the reuse of data. To achieve this, metadata and data should be well-described so that they can be replicated and/or combined in different settings.

R1. Meta(data) are richly described with a plurality of accurate and relevant attributes

R1.1. (Meta)data are released with a clear and accessible data usage license

R1.2. (Meta)data are associated with detailed provenance

R1.3. (Meta)data meet domain-relevant community standards

:::::::::::::::::::::::::






<!--  ----------------------------------------- -->
<!-- 		Best Practices (Chen+22)	-->
<!--  ----------------------------------------- -->
## Best Practices for Data Publication in the Astronomical Literature

***Link: https://iopscience.iop.org/article/10.3847/1538-4365/ac6268***

The article is dedicated for authors, and is a basis of good practices expected in journals and data-centers.

How can tou make your data FAIR?



<!--  ----------------------------------------- -->
<!-- 		Keypoints 			-->
<!--  ----------------------------------------- -->
## Small tips for your data: summary

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
<!-- -->
[vizier-publi-data-home]: https://vizier.cds.unistra.fr/vizier/submit.htx
[vizier-publi-notes-help]: https://cdsarc.cds.unistra.fr/vizier.submit/publication-notes.html
[vizier-submit-data-help]: https://cdsarc.cds.unistra.fr/vizier.submit/help.html
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

