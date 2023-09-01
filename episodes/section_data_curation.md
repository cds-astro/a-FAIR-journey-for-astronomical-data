---
title: "Data curation at CDS"
teaching: 12
exercises: 6
---

:::::::::::::::::::::::::::::::::::::: questions 

- What happens to my data after submission?
- What is the data curation?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Be aware of all the steps happening behind the curtains once your data are submitted, and before their full integration into the VO

::::::::::::::::::::::::::::::::::::::::::::::::




<!--  ----------------------------------------- -->
<!--            Data curation at CDS            -->
<!--  ----------------------------------------- -->
## What happens to your data at the CDS? 

Once the data have been submitted on the CDS servers, the VizieR team will check that the data is compatible with our standards. Once the data have been accepted, the CDS team will also add some valuable and relevant information such as metadata and links to other catalogues. This can lead to interactions with the authors, but we are trying to minimize the level of interaction.


### Behind the scenes: verifications

In addition to the semi-automated verifications already done by the programs during the different steps of the ingestion, more in-depth verifications are done by the CDS team focusing on the reliability and the quality of the catalogues.

In the following, we present some examples based on real datasets.



<!--  ----------------------------------------- -->
#### Verifications: Example 1 - Units

One key point is to the check the units.


:::::::::::::::: testimonial
#### Units corrected

In the example below the original unit for a cylindrical volume of a region (column *Size* from the figure below) was wrongly set to *cm^-3^*.

![Figure: Before -- Units as written in original paper (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_1_units_before.png){alt="Screenshot -- Table with wrong units as displayed in paper"}



Our team picked it up and wrote to the author and made the description and unit correction (field *V* from the figure below).

![Figure: After -- Units corrected in VizieR table (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_1_units_after.png){alt="Screenshot -- VizieR table with units corrected"}

<!-- https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_1_units.png -->

:::::::::::::::::::::::::


 
<!--  ----------------------------------------- -->
#### Verifications: Example 2 - Coordinates

After the units, the coordinates are the most important data the VizieR team try to gather and curate. It is the most common way to search for data.
When there are none, positions can be added from other catalogues or from SIMBAD if available. 
Alternatively, we ask for them (sometimes we have an answer). 


:::::::::::::::: testimonial
#### Coordinates corrected

Here is an example of coordinates with discrepancies when the declination is at 0 degree.

![Figure: Before -- Coordinates as written in original paper (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_2_coordinates_before.png){alt="Screenshot -- Table with wrong coordinates as made available in paper"}


Once the error detected by our team, the positions were then updated, two years after the data ingestion in VizieR.


![Figure: After -- Coordinates corrected in VizieR table (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_2_coordinates_after.png
){alt="Screenshot -- VizieR table with coordinates corrected"}

:::::::::::::::::::::::::



<!--  ----------------------------------------- -->
#### Verifications: Example 3 - Identifiers

The third important thing for our team are the identifiers. 


:::::::::::::::: testimonial
#### SIMBAD names added

To retrieve coordinates and easy the cross identification between SIMBAD and VizieR, a proper identification is needed.

Here is an example of truncated SDSS names... Impossible to retrieve except by coordinates that we have here. So the SimbadName has been added after the process for SIMBAD where misprints on coordinates have been detected. 
For this object with coordinates pointing to nothing, the right ones have been found thanks to the bibcode given in the table.

![Figure: Example of names recognized by SIMBAD added to the original table submitted to VizieR (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_3_names.png){alt="Screenshot -- VizieR table with SIMBAD-names added"}

:::::::::::::::::::::::::


<!--  ----------------------------------------- -->
#### Verifications: Example 4 - Odd values

We add mimimum and maximum values of numerical columns. It allows us to detect some oddities and it is helpful also for the astronomer who will validate the catalogue afterwards.

:::::::::::::::: testimonial
#### Min-max values added

![Figure: Example of minimum and maximum values added to a ReadMe file (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_4_minmax.png){alt="Screenshot -- VizieR ReadMe file with minimum and maximum values added to the numerical fields"}

:::::::::::::::::::::::::


<!--  ----------------------------------------- -->
#### Verifications: Example 5 - Missing data

We also add links between tables in VizieR. For instance, if an author said that magnitudes come from this survey, we actually point to that survey so we can verify the values. If a table contains galaxy clusters, we can add the number of galaxies per cluster.

Adding those links helps us to detect errors and missing data.


:::::::::::::::: testimonial
#### Missing data retrieved

In the example below, the link between the two tables is the number of S43GHz flux measurements (column *Nc* from the figure below). 

When the data were first ingested, and it is still the case in the MRT table available with the paper, there was no measurement (*Nc = 0*).

We contacted the author to get the corresponding data and thus we can now plot the light curve of this object in VizieR.


![Figure: Example of missing data retrieved, adding more visibility to the original set (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_5_missing_data.png
){alt="Screenshot -- Missing data retrieved by the CDS team enabling a better reusability of the original data"}

:::::::::::::::::::::::::


<!--  ----------------------------------------- -->
#### Verifications: Example 6 - Missing common key 

Last but not least, to add links between tables we need a common key (e.g identifier, coordinates ...).


:::::::::::::::: testimonial

#### Cross-identification between tables

In the two figures below, we can see an example taken from a paper with two tables (*Tables A and B*) with two similar first columns in both:

- Name of the stellar system to which the star belongs
- Name of the star

However, it is not obvious that Bel10018 (SimbadName: [BFO2002] UMi 10018) mentionned in *Table A* corresponds to COS 347 in *Table B*.

![Figure: Extract of Table A from paper (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_6_missing_key_table1.png){alt="Screenshot -- Table A as displayed in paper"}


![Figure: Before -- extract of Table B from paper (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_6_missing_key_table2_before.png){alt="Screenshot -- Table B as displayed in paper"}


As there are no common identifier or coordinates repeated in the second table, the only alternative would have been to go through the list of references cited (3rd column of *Table B*) to get the coordinates and identify the object one by one.
Therefore, the CDS team contacted the author to get the names and positions for *Table B* and create a better link between the two tables as displayed below.

![Figure: After -- extract of Table B as available in VizieR (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_6_missing_key_table2_after.png){alt="Screenshot -- Table B updated as available on VizieR"}


:::::::::::::::::::::::::



<!--  ----------------------------------------- -->
### Errata

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

## Summary: Data submission and curation

::::::::::::::::::::::::::::::::::::: keypoints

2 options for data submission:

- Online interface
- File Transfer Protocol

The CDS provides tools to build *ReadMe* file and aligned ASCII tables (Machine Readable Table in FORTRAN format).

- No need to build it from scratch!

The *ReadMe* file describe your tables by providing all necessary information to locate the catalogue (authors, title, abstract, keywords, acknowledgments, ...).

- This highly standardised file allows reusability and cross matching between catalogues.
- A good description of your data is the key to discoverability. 

Once the catalogues are submitted, a delay is needed for VizieR curation and validation before full ingestion!

- Verifications leading to corrections: ~ 30% of the references
- Main corrections: identifiers, coordinates, units ...

You cannot Find, Access and Re-use data if the coordinates/identifiers are not right!


::::::::::::::::::::::::::::::::::::::::::::::::


<!--  ----------------------------------------- -->
<!--            Next Chapters                   -->
<!--  ----------------------------------------- -->
## Next chapters

In the next chapters, you will learn what happen to your data once they are fully ingested into VizieR.
 


<!--  ----------------------------------------- -->
<!-- 		Link references			-->
<!--	==> See links.md file			-->
<!--  ----------------------------------------- -->

