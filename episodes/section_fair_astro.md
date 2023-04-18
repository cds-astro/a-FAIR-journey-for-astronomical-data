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
- Be aware of how to publish your data in the existing and new Open Science systems,  keeping in mind the Virtual Observatory (VO) standards.

::::::::::::::::::::::::::::::::::::::::::::::::



<!--  ----------------------------------------- -->
<!-- 		Introduction 			-->
<!--  ----------------------------------------- -->
## Introduction

The set of guidelines for making research (meta)data findable, accessible, interoperable and reusable that ultimately ensures standardised machine actionability.


![FAIR guiding principles for data resources](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/FAIR_data_principles.jpg){alt="Findable Accessible Interoperable Reusable principes"}
*Credit: SangyaPundir, CC BY-SA 4.0 <https://creativecommons.org/licenses/by-sa/4.0>, via Wikimedia Commons*






<!--  ----------------------------------------- -->
<!-- 		Best Practices (Chen+22)	-->
<!--  ----------------------------------------- -->
## Best Practices for Data Publication in the Astronomical Literature

***Link: https://iopscience.iop.org/article/10.3847/1538-4365/ac6268***

The article is dedicated for authors, and is a basis of good practices expected in journals and data-centers.



<!--  ----------------------------------------- -->
<!-- 		Keypoints 			-->
<!--  ----------------------------------------- -->
## Raise the odds to be included in VizieR!

::::::::::::::::::::::::::::::::::::: keypoints

- For tables containing known astronomical objects, an existing **non-altered** name must be given along with the coordinates.
- All columns must be explained with **their corresponding unit**.
- Your columns should be homogeneous, and you should avoid mixing measurements with different meanings: errors mixed with limts, or values with different units (that should be in different columns).
- When there is more than one table, the objects in common must be identified with the **same name between tables**.

::::::::::::::::::::::::::::::::::::::::::::::::



<!--  ----------------------------------------- -->
<!-- 		Ideas	 			-->
<!--  ----------------------------------------- -->
## *Ideas*

Extract from: https://carpentries-incubator.github.io/managing-computational-projects/09-rdm.html

Making data ‘FAIR’ is not the same as making it ‘open’. Accessible means that there is a procedure in place to access the data. Data should be as open as possible, and as closed as necessary. It is also important to say that the FAIR principles are aspirational: they do not strictly define how to achieve a state of FAIRness, but rather describe a continuum of features, attributes, and behaviours that will move a digital resource closer to that goal. Even though the FAIR principles have been defined to allow machines to find and use digital objects automatically, they improve the reusability of data by humans as well. The capacity of computational systems to find, access, interoperate, and reuse data, with minimal human intervention, is essential in today’s data-driven era.

You can find a more detailed overview of the FAIR principles by GO FAIR of what the FAIR principles recommend.


https://carpentries-incubator.github.io/fair-data-management-agriculture/fair-data.html


- Fix "bad examples"??


<!--  ----------------------------------------- -->
<!-- 		Documentation 			-->
<!--  ----------------------------------------- -->
## More documentation (from Vizier)

- [Preparing and Submitting Tabular Data][vizier-publi-data-home]
- [VizieR catalogue upload generalities][vizier-publi-notes-help]
- [The submitting VizieR page documentation][vizier-submit-data-help]



<!--  ----------------------------------------- -->
<!-- 		Link references			-->
<!--  ----------------------------------------- -->
[vizier-publi-data-home]: https://vizier.cds.unistra.fr/vizier/submit.htx
[vizier-publi-notes-help]: https://cdsarc.cds.unistra.fr/vizier.submit/publication-notes.html
[vizier-submit-data-help]: https://cdsarc.cds.unistra.fr/vizier.submit/help.html
