---
title: "Data curation at CDS"
teaching: 5
exercises: 0
---

:::::::::::::::::::::::::::::::::::::: questions 

- What happens to your data after submission to VizieR?
- What is the data curation?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Create FAIR tables, integrating "key" columns
- Summarize all the steps happening behind the curtains once your data are submitted, and before their full integration into the VO

::::::::::::::::::::::::::::::::::::::::::::::::



<!--  ----------------------------------------- -->
<!-- 	Intro 					-->
<!--  ----------------------------------------- -->
## Overview

Once the data have been submitted on the CDS servers, the VizieR team will check that the data are compatible with standards. Once the data have been accepted, the CDS team will also add some valuable and relevant information such as metadata and links to other catalogues. This can lead to interactions with the authors, but we are trying to minimize the level of interaction.


![Figure: Journey from a publication to EOSC, step 4 "curation & verification"](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/lighthouse/step3.svg){alt="Figure -- Summary data journey from a publication to VizieR and then EOSC: fourth step of the journey - step curation and verification of the data, right after - step data published in a refereed paper, step preparation of the data, step submission of the data"}



## Behind the scenes: verifications

In addition to the semi-automated verifications already done by the programs during the different steps of the ingestion, more in-depth verifications are done by the CDS team focusing on the reliability and the quality of the catalogues.

In the following, we present some examples based on real datasets.



<!--  ----------------------------------------- -->
### Verifications: Example 1 - Units

One key point is to the check the units.


:::::::::::::::: testimonial
#### Units corrected

<!-- Link to journal: Biny 2017 // https://iopscience.iop.org/article/10.3847/1538-3881/aa88d0#ajaa88d0t2 -->

In the example below the original unit for a cylindrical volume of a region (column *Size* from the figure below) was wrongly set to *cm^-3^*.

![Figure: Before -- Units as written in original paper (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_1_units_before.png){alt="Screenshot -- Table with wrong units as displayed in paper"}



Our team picked it up and wrote to the author and made the description and unit correction (field *V* from the figure below).

![Figure: After -- Units corrected in VizieR table (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_1_units_after.png){alt="Screenshot -- VizieR table with units corrected"}

:::::::::::::::::::::::::


 
<!--  ----------------------------------------- -->
### Verifications: Example 2 - Coordinates

After the units, the coordinates are the most important data the VizieR team try to gather and curate. It is indeed the most common way to search for data in VizieR.


:::::::::::::::: testimonial
#### Coordinates corrected

<!-- Link to paper: https://iopscience.iop.org/article/10.3847/0004-637X/822/2/59#apj522819t1 // Table 1-->

Here is an example of coordinates with discrepancies when the declination is at 0 degree.

![Figure: Before -- Coordinates as written in original paper (screenshot). The following columns are displayed: Seq (catalog index number);  BGPS source identifier; Hour, Minute and Second of Right Ascension (J2000);  Sign, Degree, Arcminute, Arcsecond of the Declination (J2000).](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_2_coordinates_before.png){alt="Screenshot -- Table with wrong coordinates as made available in paper"}


<!-- Link to Readme: J/ApJ/822/59 // https://cdsarc.cds.unistra.fr/viz-bin/ReadMe/J/ApJ/822/59?format=html&tex=true // clumps-->
Once the error detected by our team (missing minus sign for some Declinations), the positions were then updated, two years after the data ingestion in VizieR.

![Figure: After -- Coordinates corrected in VizieR table (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_2_coordinates_after.png
){alt="Screenshot -- VizieR table with coordinates corrected"}

:::::::::::::::::::::::::


When there are none, positions can be added from other catalogues or from SIMBAD if available. 
Alternatively, we ask for them (sometimes we have an answer). 

:::::::::::::::: testimonial
#### Coordinates added

<!-- Link to paper: https://iopscience.iop.org/article/10.3847/1538-4357/ac0fda#apjac0fdat3 // Table 3-->
In the following example, we can see that no coordinate was provided in the original table. 

![Figure: Before -- Columns as written in original table (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_2_coordinates_added_before.png){alt="Screenshot -- Table without coordinates as available in paper"}


<!-- Link to Readme: J/ApJ/919/121  // https://vizier.cds.unistra.fr/viz-bin/VizieR-3?-source=J/ApJ/919/121/table3&-out.max=50&-out.form=HTML%20Table&-oc.form=sexa // table 3 -->
Using SIMBAD or otherwise the HASH PN databases (when no SIMBAD corresponding match has been found -- SimbadName empty), we were able to complement this table with positions.

![Figure: After -- Coordinates added in VizieR table (screenshot). The 4 columns in color are computed by VizieR, and not part of the original data.](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_2_coordinates_added_after.png){alt="Screenshot -- Table with SimbadName and coordinates informations added to the original columns"}


:::::::::::::::::::::::::


<!--  ----------------------------------------- -->
### Verifications: Example 3 - Identifiers

The third important thing for our team are the identifiers. 


:::::::::::::::: testimonial
#### SIMBAD names added + misprint on names corrected

<!-- Link to VizieR: J/ApJ/833/20  // https://vizier.cds.unistra.fr/viz-bin/VizieR?-source=J/ApJ/833/20 // table 1 -->

To retrieve coordinates and easy the cross identification between SIMBAD and VizieR, a proper identification is needed.

Here is an example of truncated SDSS names... Impossible to retrieve except by coordinates that we luckily have in this case. So the SimbadName has been added after the process for SIMBAD where misprints on coordinates have been detected (identified by the column *f_Name* set to *o* below). 
For this object with coordinates pointing to nothing, the right ones have been found thanks to the bibcode given in the table.

![Figure: Example of names recognized by SIMBAD added to the original table submitted to VizieR (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_3_names.png){alt="Screenshot -- VizieR table with SIMBAD-names added and misprint on names (in the declinaison) corrected"}

:::::::::::::::::::::::::




<!--  ----------------------------------------- -->
### Verifications: Example 4 - Odd values

We add mimimum and maximum values of numerical columns. It allows us to detect some oddities and it is helpful also for the astronomer who will validate the VizieR catalogue afterwards.

:::::::::::::::: testimonial
#### Min-max values added

<!-- Link to VizieR: J/A+A/569/A17 // https://cdsarc.cds.unistra.fr/viz-bin/ReadMe/J/A+A/569/A17?format=html&tex=true -->

![Figure: Example of minimum and maximum values (in brackets) added to a ReadMe file (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_4_minmax.png){alt="Screenshot -- VizieR ReadMe file with minimum and maximum values added to the numerical fields"}

:::::::::::::::::::::::::


<!--  ----------------------------------------- -->
### Verifications: Example 5 - Link between tables

We also add links between tables in VizieR. For instance, if an author said that magnitudes come from a certain survey, we actually point to that survey so we can verify the values. If a table contains galaxy clusters and another the membership, we can add the number of galaxy members per cluster, assuming the cluster names are the same in both tables.

Adding those links helps us to detect errors and missing data.


:::::::::::::::: testimonial
#### Link between tables added

<!-- Link to Vizier: J/ApJ/910/135 // https://cdsarc.cds.unistra.fr/viz-bin/cat/J/ApJ/910/135 -->

In the example below, the column *Nz* (Number of high-z galaxies in a given cluster) has been added to the original Table 1 to create a link with the relics-z table. 

![Figure: Example of column added to the original set -- Table 1 -- , adding more visibility to the data (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_5_link_table_1.png){alt="Screenshot -- Link between columns added by the CDS team enabling a better reusability of the original data"}

By clicking on the value "14" from the column *Nz* for the cluster "plckg004-19", one will get automatically the corresponding rows from the relics-z table, without any extra filtering, as illustrated below.

![Figure: Example of column added to the original set -- relics-z table -- , adding more visibility to the data (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_5_link_table_2.png){alt="Screenshot -- Link between columns added by the CDS team enabling a better reusability of the original data, and a quicker access to the corresponding results"}


:::::::::::::::::::::::::


<!--  ----------------------------------------- -->
### Verifications: Example 6 - Missing common key 

Last but not least, to add links between tables we need a common key (e.g identifier, coordinates ...).


:::::::::::::::: testimonial

#### Cross-identification between tables

<!-- Link to paper: Kirby 2018 // https://iopscience.iop.org/article/10.3847/1538-4365/aac952#apjsaac952t1 // table 3 (A) and table 5 (B) -->

In the two figures below, we can see an example taken from a paper with two tables (*Tables A and B*) with two similar first columns in both:

- Name of the stellar system to which the star belongs
- Name of the star

However, it is not obvious that Bel10018 (SimbadName: [BFO2002] UMi 10018) mentionned in *Table A* corresponds to COS 347 in *Table B*.

![Figure: Before -- Extract of Table A from paper (screenshot). The following columns are displayed: Name of stellar system, Star name, RA (J2000), DEC (J2000), Bmag, Vmag, Rmag, CoFe, e_CoFe, NiFe, e_NiFe.](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_6_missing_key_table1.png){alt="Screenshot -- Table A as displayed in paper"}



![Figure: Before -- extract of Table B from paper (screenshot). The following columns are displayed: Name of the stellar system, Star name, Reference for HRS abundances, Cr-HRS, e_Cr-HRS, Co-HRS.](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_6_missing_key_table2_before.png){alt="Screenshot -- Table B as displayed in paper"}


<!-- Link to Vizier: J/ApJS/237/18 // https://cdsarc.cds.unistra.fr/viz-bin/cat/J/ApJS/237/18 -->

As there are no common identifier or coordinates repeated in the second table, the only alternative would have been to go through the list of references cited (3rd column of *Table B*) to get the coordinates and identify the object one by one.
Therefore, the CDS team contacted the author to get the names and positions for *Table B* and create a better link between the two tables as displayed below.

![Figure: After -- extract of Table B as available in VizieR (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_6_missing_key_table2_after.png){alt="Screenshot -- Table B updated as available on VizieR"}


:::::::::::::::::::::::::



<!--  ----------------------------------------- -->
## Errata

As said before, the VizieR database is evolving every day: with new catalogues being added or old ones being updated. 


:::::::::::::::: testimonial
#### Tables updated

In the example below, one table from the original catalogue was updated, to reflect the changes published in an erratum.

![Figure: Example of a table updated following erratum publication (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_7_errata.png){alt="Screenshot -- Table from catalogue updated to be consistent with erratum publication"}

:::::::::::::::::::::::::





<!--  ----------------------------------------- -->
<!--            Data curation at CDS            -->
<!--  ----------------------------------------- -->
## Data available to all

Once the data are public, they are accessible as plain files in [FTP directories at CDS][vizier-catalogue-collection] and other participating [data centers][vizier-mirors] (e.g. at [CfA/Harvard (USA)][vizier-at-cfa] or [NOAJ/ADAC (Japan)][vizier-at-noaj]), as well as all VO compatible services.


![Figure: Journey from a publication to EOSC, step 4 "curation & verification"](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/lighthouse/step4.svg){alt="Figure -- Summary data journey from a publication to VizieR and then EOSC: fourth step of the journey - step curation and verification of the data, right after - step data published in a refereed paper, step preparation of the data, step submission of the data"}



<!--  ----------------------------------------- -->
<!--            Summary                         -->
<!--  ----------------------------------------- -->

## Summary: What happens to your data at CDS?

::::::::::::::::::::::::::::::::::::: keypoints

Once the catalogues are submitted, a delay is needed for VizieR curation and validation before full ingestion!

The validation process involves some:

- Verifications leading to corrections: ~ 30% of the references
- Main corrections: identifiers, coordinates, units ...

You cannot Find, Access and Re-use data if the coordinates/identifiers are not right!


::::::::::::::::::::::::::::::::::::::::::::::::


<!--  ----------------------------------------- -->
<!--            Next Chapters                   -->
<!--  ----------------------------------------- -->
## Next chapters

In the next chapters, you will learn what happen to your fully ingested data when they continue their journey into the Virtual Observatory and up to EOSC. 
 


<!--  ----------------------------------------- -->
<!-- 		Link references			-->
<!--	==> See links.md file			-->
<!--  ----------------------------------------- -->


<!--  ----------------------------------------- -->
<!-- Transform link a/href with target="_blank" -->
<!-- Open them in a new window			-->
<!--  ----------------------------------------- -->
<script>
document.querySelectorAll('#main-content a:not([target])').forEach(link => link.setAttribute('target', '_blank'))
</script>

