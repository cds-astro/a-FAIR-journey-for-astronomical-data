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

Officialy formalized by Wilkinson et al. in 2016 ([10.1038/sdata.2016.18][wilkinson_2016]), the FAIR Guiding Principles have emerged over the last few years. The underlying idea is to provide a set of guidelines for making research (meta)data **f**indable, **a**ccessible, **i**nteroperable and **r**eusable that ultimately ensures standardised machine actionability. 

Many great courses can be found online explaining those principles in more details.
In this section, we will summarize them and focus more on what it means for astronomical data. 
 
![FAIR guiding principles for data resources](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/fair_principles.png){alt="Findable Accessible Interoperable Reusable principes"}
*Credit: Open Science Training Handbook, CC0 1.0 Universal, https://doi.org/10.5281/zenodo.1212496*



::::::::::::::::::::::::::::::::::::::: discussion

### Details

bla bla bla

:::::::::::::::::::::::::::::::::::::::::::::::::::

:::::::::::::::: solution

### Findable

**F**ind the data available

:::::::::::::::::::::::::


:::::::::::::::: solution

### Accessible

**A**ccessible and not open!


Extract from: https://carpentries-incubator.github.io/managing-computational-projects/09-rdm.html

Making data ‘FAIR’ is not the same as making it ‘open’. Accessible means that there is a procedure in place to access the data. Data should be as open as possible, and as closed as necessary. It is also important to say that the FAIR principles are aspirational: they do not strictly define how to achieve a state of FAIRness, but rather describe a continuum of features, attributes, and behaviours that will move a digital resource closer to that goal. Even though the FAIR principles have been defined to allow machines to find and use digital objects automatically, they improve the reusability of data by humans as well. The capacity of computational systems to find, access, interoperate, and reuse data, with minimal human intervention, is essential in today’s data-driven era.

You can find a more detailed overview of the FAIR principles by GO FAIR of what the FAIR principles recommend.


https://carpentries-incubator.github.io/fair-data-management-agriculture/fair-data.html





:::::::::::::::::::::::::


:::::::::::::::: solution

### Interopable

**I**nteroperable use of the data with other data

:::::::::::::::::::::::::


:::::::::::::::: solution

### Reusable

**R**e-use the data

:::::::::::::::::::::::::






<!--  ----------------------------------------- -->
<!-- 		Best Practices (Chen+22)	-->
<!--  ----------------------------------------- -->
## Best Practices for Data Publication in the Astronomical Literature

***Link: https://iopscience.iop.org/article/10.3847/1538-4365/ac6268***

The article is dedicated for authors, and is a basis of good practices expected in journals and data-centers.



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
<!-- 		Other images			-->
<!--  ----------------------------------------- -->
## Extra images ???

![FAIR guiding principles for data resources](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/FAIR_data_principles.jpg){alt="Findable Accessible Interoperable Reusable principes"}
*Credit: SangyaPundir, CC BY-SA 4.0 <https://creativecommons.org/licenses/by-sa/4.0>, via Wikimedia Commons*



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
