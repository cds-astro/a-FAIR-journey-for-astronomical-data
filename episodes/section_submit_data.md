---
title: "Submitting astronomical data"
teaching: 9
exercises: 0
---

:::::::::::::::::::::::::::::::::::::: questions 

- How and where to submit your data?
- What is a *ReadMe* file?
- Do and don't when submitting data
- What is the data curation?

::::::::::::::::::::::::::::::::::::::::::::::::

::::::::::::::::::::::::::::::::::::: objectives

- Be aware of how to submit your data in the existing and new Open Science systems,  keeping in mind the Virtual Observatory (VO) standards.

::::::::::::::::::::::::::::::::::::::::::::::::


<!--  ----------------------------------------- -->
<!-- 		Submitting 			-->
<!--  ----------------------------------------- -->
<!-- Source: https://cdsarc.cds.unistra.fr/vizier.submit/publication-notes.html#section4 -->
<!-- Source: https://vizier.cds.unistra.fr/vizier/submit.htx // Section 4 -->
## Where to deposit the data?

Two routes are possible to submit your data to VizieR:

- Option 1: Use the submission [**online interface**][vizier-submit-login]
	- The upload will generate a *ReadMe* file based on your tables.
	- Some basic checks on the *ReadMe* and data files are performed. 
	- It also includes FITS ingestion procedure to improve the discoverability of images and spectra.
- Option 2: Use the [**Python cdspyreadme library**][vizier-cdspyreadme] to create the *ReadMe* file and then upload all the tables and other data by [**FTP**][vizier-ftp-login]


<!-- #### Special case: large volumetry -->
The submission web application is an HTTP service and depends of authors network. The process is dedicated for tables size less than 100Mb but accepts tables until ~200Mb. 


<!-- Contact CDS -->
For larger files or any other questions, please contact the VizieR staff: [cats(at)cdsarc.u-strasbg.fr](mailto:cats@cdsarc.u-strasbg.fr).


![Journey from a publication to EOSC: third step of the journey - step submission of the data](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/lighthouse/step2.svg){alt="Figure -- Summary data journey from a publication to VizieR and then EOSC: third step of the journey - step submission of the data, right after - step data published in a refereed paper, step preparation of the data"}




<!--  ----------------------------------------- -->
<!--   ReadMe files                             -->
<!--  ----------------------------------------- -->
## ReadMe Files

<!-- Source: https://vizier.cds.unistra.fr/vizier/submit.htx  // Section 3 -->
### The why and what of the ReadMe file

To be reusable, any data needs extra information. In astronomy, the convention is to give this information (authors, title, references, summary, etc...) in a separate file called *ReadMe*. 

Every catalogue in the Virtual Observatory registry has its own *ReadMe*.
Numerous examples can be found on the [FTP directories][vizier-ftp-cats] at CDS.
A typical illustration could be e.g. [J/A+A/382/389/ReadMe][vizier-readme-example]. 



<!-- Blank template -->
Here is a blank template: 

```
$catalogue                                                      ($author, $date)
================================================================================
$title
    $authors
    $bibcode
================================================================================
Keywords: $keywords

Abstract:
    $abstract

Description:
    $description


Objects:
    --------------------------------------------------
      RA  (equinox)  DE     Name(s)
    --------------------------------------------------
    hh mm ss.s +dd mm ss    Name1 = Name1
    --------------------------------------------------


File Summary:
--------------------------------------------------------------------------------
 FileName    Lrecl   Records    Explanations
--------------------------------------------------------------------------------
$tablesIndex
--------------------------------------------------------------------------------


See also:
    $seealso


Nomenclature notes:
    $nomenclature


Byte-by-byte Description of file: $bytebybyte.file
--------------------------------------------------------------------------------
   Bytes Format Units   Label    Explanations
--------------------------------------------------------------------------------
$bytebybyte
--------------------------------------------------------------------------------
Note (n): $note 
--------------------------------------------------------------------------------


Acknowledgements: $acknowledgments


References:
================================================================================
(End)                            $modification_done_by	      $date_modification
```

----------------------------


<!--  ----------------------------------------- -->
### Full description of the content of the ReadMe File

The [Standards for Astronomical Catalogues][vizier-readme-std] gives a complete description of the standard for *ReadMe* files. A general overview and some examples are given below.



:::::::::::::::::::::::::::::::::::::: callout

# Disclaimer
In this section, we give a lot of details (as we are dissecting the contents of the *ReadMe*). It can be overwhelming, but the next section covers the tools that exist to help generating a correct *ReadMe* file. 

You don't necessarily need to build it from scratch!

::::::::::::::::::::::::::::::::::::::



<!-- Details of the template -->
::::::::::::::::::::::::::::::::::::::: discussion

### Details
The *ReadMe* file contains severals sections.

As a general rule, only **section headers are left flushed, while the text is indented** — with the noticeable exceptions of the title, the file names in the File Summary section, and of [Note headers][vizier-cat-35-lengthy]. 

No line in this description file can exceed 80 characters; it is moreover suggested to limit the textual parts to 70 characters, such that a conversion to FITS could keep the text as COMMENT cards.

:::::::::::::::::::::::::::::::::::::::::::::::::::


<!-- ---------------- -->
:::::::::::::::: solution
### 1. First line

Catalogue designation, an abbreviated title followed within parenthesis by the last name of the first author, a + sign if there are multiple authors, and the year — this information has to be condensed in a single line of 80 characters or les. 

For the **volume** and **page numbers**:
- For papers accepted for publication in A&A -- but not yet published -- these will be added directly at CDS,
- For papers accepted in other journals, it is recommended to send them via email (to [cats(at)cdsarc.u-strasbg.fr](mailto:cats@cdsarc.u-strasbg.fr)) when you get these details.

:::::::::::::::::::::::::


:::::::::::::::: solution
######  >>> Example 1
```
I/221               The Magellanic Catalogue of Stars - MACS (Tucholke+ 1996)
================================================================================
```
:::::::::::::::::::::::::



<!-- ---------------- -->
:::::::::::::::: solution
### 2. Full title(s), authors, and reference(s) of the catalogue 

Each title is left-adjusted (no indentation); the line(s) containing the authors' names are indented (at least two blanks), and the bibliographic reference is enclosed between angle brackets. The BibCode is introduced by an equal sign, as a word without embedded blank of exactly 20 characters (with the equal sign).
:::::::::::::::::::::::::

:::::::::::::::: solution
######  >>> Example 2
```
The Magellanic Catalogue of Stars - MACS
     Tucholke H.-J., de Boer K.S., Seitter W.C.
    <Astron. Astrophys. Suppl. Ser., 119, 91-98 (1996)>
    <The Messenger 81, 20 (1995)>
    =1996A&AS..119...91T 
    =1995Msngr..81...20D
================================================================================
```
:::::::::::::::::::::::::



<!-- ---------------- -->
:::::::::::::::: solution
### 3. 'Keywords' header


Three categories of keywords can be added:

- *Keywords*: introduces the list of keywords as in the printed publication.
- *ADC\_Keywords*: introduces the list of data-related keywords (see [ADC_keywords and their VizieR translation][vizier_adc_keywords] for more details). They are strictly related to the tabular material collected in the paper.
- *Mission\_Name*: for data originated from satellite mission, this header precedes the satellite name.


Whatever the category, multiple keywords are separated by a semicolon (;) or a dash (-) embedded in blanks.
:::::::::::::::::::::::::

:::::::::::::::: solution
######  >>> Example 3
```
ADC_Keywords: Clusters, galaxy ; Galaxies, photometry ; Photometry, CCD
Keywords: galaxies: clusters - galaxies: elliptical and lenticular, cD -
          cosmology: large-scale structure of Universe
```
:::::::::::::::::::::::::



<!-- ---------------- -->
:::::::::::::::: solution
#### 4. 'Abstract' and 'Description' headers

The **Description** part gives the *context of the data*, such as instrumentation or observing conditions. 
It therefore differs from the **Abstract** which describes the *scientific results* that the author(s) derived from the data.
:::::::::::::::::::::::::

:::::::::::::::: solution
######  >>> Example 4
```
Abstract:
    We present the results of a study of streaming motion of galaxy
    clusters around the Giant Void (RA~13h, DE~40{deg}, z~0.11 and a
    diameter of 150/hMpc) in the distribution of rich Abell clusters. We
    used the Kormendy relation as a distance indicator taking into account
    galaxy luminosities. Observations were carried out in Kron-Cousins
    R_c_ system on the 6m and 1m telescopes of SAO RAS. For 17 clusters in
    a spherical shell of 25/hMpc in thickness centered on the void no
    significant diverging motion (expected to be generated by the mass
    deficit in the void) has been detected. This implies that cosmological
    models with low {Omega}_m_ are preferred. To explain small mass
    underdensity inside the Giant Void, a mechanism of void formation with
    strong biasing is required.

Description:
    Photometric parameters for 210 early-type galaxies in the central
    regions for 17 clusters around the Giant Void are presented. Galaxies
    in the following clusters have been observed:
    A1298, A1361, A1427, A1468, A1542, A1551, A1609, A1637, A1666,
    A1691, A1700, A1739, A1793, A1823, A1834, A1885, and A1894.
    For each galaxy equatorial coordinates, total magnitudes in R_c_
    (Kron-Cousins) band, effective radius, surface brightness and mean
    surface brightness are given. The derivation of the effective
    parameters takes the seeing into account.
```
:::::::::::::::::::::::::



<!-- ---------------- -->
:::::::::::::::: solution
#### 5. (optional) 'Objects' header
The list of **observed objects** can be used when no data table contains the list and position of the astronomical objects observed or studied, as for example in the study of a high-resolution spectrum of a single star. Such a list is normally restricted to very few objects – less than 10 or 20 typically.

:::::::::::::::::::::::::


<!-- ---------------- -->
:::::::::::::::: solution
#### 6. 'File Summary' header
It describes the files composing the set. Each file should be described by its *filename*, the *length of the longest line* (Lrecl), the *number of lines* (Records), and a *caption* (short title). Lengthy notes can be added if necessary.
:::::::::::::::::::::::::

:::::::::::::::: solution
######  >>> Example 6
```
File Summary:
--------------------------------------------------------------------------------
 FileName      Lrecl    Records    Explanations
--------------------------------------------------------------------------------
ReadMe            80          .   This file
clusters.dat      45         17   Cluster positions and magnitudes (from Simbad)
table2.dat        57        210   Photometric parameters for 210 galaxies
                                   in 17 clusters
--------------------------------------------------------------------------------
```
:::::::::::::::::::::::::


<!-- ---------------- -->
:::::::::::::::: solution
#### 7. 'See also' header
This section can be used to list related catalogues, data sets or services. Each catalog or service starts on a new line, and is followed by a colon embedded in blanks.

:::::::::::::::::::::::::

:::::::::::::::: solution
######  >>> Example 7
```
See also:
    J/A+AS/97/729 : O-rich stars in 1-20um range
    http://machine/description.html : Detailed Description
```
:::::::::::::::::::::::::


<!-- ---------------- -->
:::::::::::::::: solution
#### 8. (optional) 'Nomenclature Notes' header

This  header provides valuable information related to the nomenclature of astronomical objects.
:::::::::::::::::::::::::



<!-- ---------------- -->
:::::::::::::::: solution
#### 9. 'Byte-by-byte Description of file' header

This section describes the structure of each data files (files with the .dat extension).
This description is made in a tabular form, each row describing one field (column) of the data file.

The description is presented as a five-column table with the following elements:

- the *starting* (from 1) and *ending* byte of column, separated by a dash -; this dash is however not required for a single-byte column.
- the *format* of the field, written as a *fortran-like* format
    + **A***n*      for a character column made of *n* characters;
    + **I***n*      for a column containing an integer number of *n* digits;
    + **F***n.d*    for a column containing a float number of width *n* digits and up to *d* digits in the fractional part;
    + **E***n.d*    for a number using the exponential notation;
- the [units][vizier-cat-32-units] used in the field. **SI** units are strongly encouraged, avoid the CGS units (for instance, use **mW/m2** instead of **ergs/s/cm2**).
- the *label* (heading) of the field, made of a single word (*no embedded blank*); a few [basic conventions][vizier-cat-33-labels] are used for usual parameters (e.g. positions) and related quantities (e.g. mean errors).
- a short *explanations* of the contents of the column. 
This last field may also specify: the available range of the value in the column (using **[...]**), the possibility of having unspecified or NULL values (using **?**), the order of the values within the table (increasing or decreasing order). More details can be found [here][vizier-cat-34-explanations].
:::::::::::::::::::::::::

:::::::::::::::: solution
######  >>> Example 9
```
Byte-by-byte Description of file: clusters.dat
--------------------------------------------------------------------------------
   Bytes Format Units   Label    Explanations
--------------------------------------------------------------------------------
   1-  4  I4    ---     Abell    Abell (ACO) cluster number
   7-  8  I2    h       RAh      Right ascension (J2000.0)
  10- 11  I2    min     RAm      Right ascension (J2000.0)
  13- 16  F4.1  s       RAs      Right ascension (J2000.0)
      18  A1    ---     DE-      Declination sign (J2000.0)
  19- 20  I2    deg     DEd      Declination (J2000.0)
  22- 23  I2    arcmin  DEm      Declination (J2000.0)
  25- 26  I2    arcsec  DEs      Declination (J2000.0)
  29- 45  A17   ---     Names    Other name (1)
--------------------------------------------------------------------------------
Note (1): We identify the cluster ACO 1666 with ZwCl J1303.7+5118 as the
    Abell cluster coordinates (J1302.8+5153) none rich cluster was found.
    Coordinates refer to the main concentration of galaxies.
--------------------------------------------------------------------------------

Byte-by-byte Description of file: table2.dat
-----------------------------------------------------------------------------
   Bytes Format  Units         Label     Explanations
-----------------------------------------------------------------------------
   1-  4  I4     ---           Abell     Abell (ACO) cluster number
   6-  7  I2     ---           Galaxy    Galaxy identification number
   9- 10  I2     h             RAh       Right Ascension J2000 (hours)
  12- 13  I2     min           RAm       Right Ascension J2000 (minutes)
  15- 19  F5.2   s             RAs       Right Ascension J2000 (seconds)
      21  A1     ---           DE-       Declination J2000 (sign)
  22- 23  I2     deg           DEd       Declination J2000 (degrees)
  25- 26  I2     arcmin        DEm       Declination J2000 (minutes)
  28- 31  F4.1   arcsec        DEs       Declination J2000 (seconds)
  33- 37  F5.2   mag           Rcmag     Asymptotic Kron-Cousins R_c_ band
                                          magnitude corrected for Galactic
                                          extinction (1)
  39- 43  F5.2   arcsec        reff      Seeing corrected effective radius (2)
  45- 49  F5.2   mag/arcsec2   mue       Seeing corrected surface
                                          brightness at reff (1), (2)
  51- 55  F5.2   mag/arcsec2   <mue>     Seeing corrected mean surface
                                          brightness within reff (1), (2)
      57  I1     ---           ExclFlag  [1,3]? Exclusion flag (3)
--------------------------------------------------------------------------------
Note (1): Correction for foreground Galactic extinction according to Schlegel
     et al. (1998ApJ...500..525S) corresponds to the centre of cluster
Note (2): Correction for seeing effect following Saglia et al.
     (1993MNRAS.264..961S)
Note (3): 33 galaxies excluded from the distance determination:
     1 = fainter than M_R_~-21.5mag
     2 = disk dominated
     3 = peculiar or interacting
--------------------------------------------------------------------------------
```
:::::::::::::::::::::::::


<!-- ---------------- -->
:::::::::::::::: solution
#### 10. (optional)  Global notes header

Notes which apply to several tables are introduced by *Note (Gn):*  n being the number of the global note referenced in the Byte-by-byte Description of file:  sections.
:::::::::::::::::::::::::


<!-- ---------------- -->
:::::::::::::::: solution
#### 11. (optional)  'History', 'Acknowledgements' headers

Some other sections may exist when required, e.g. **History**;  introduces notes about the modification history, **Acknowledgements:**  etc...
:::::::::::::::::::::::::

:::::::::::::::: solution
######  >>> Example 11
```
Acknowledgements: Alexander Kopylov <akop@sao.ru>
```
:::::::::::::::::::::::::


<!-- ---------------- -->
:::::::::::::::: solution
#### 12. (optional) 'References' header

This section contains the necessary references. Bibcodes are strongly encouraged, to enable an automatic link to the existing Abstract Services like ADS.

For large sets of references, you can also gather them into a dedicated *reference file* named **refs.dat**.
:::::::::::::::::::::::::

:::::::::::::::: solution
######  >>> Example 12
```
References:
  Kopylova & Kopylov, 1998PAZh...24..573K, (1998AstL...24..491K)
    Structure and dynamic state of the Corona Borealis supercluster
```
:::::::::::::::::::::::::


<!-- ---------------- -->
:::::::::::::::: solution
#### 13. Last line

The very last line includes just the left-flushed word **(End)**, the name of the person who took care of the standardisation, and the date of the last modification.
:::::::::::::::::::::::::

:::::::::::::::: solution
######  >>> Example 13
```
================================================================================
(End)                            Alexander Kopylov [SAO, Russia]     06-Feb-2002
```
:::::::::::::::::::::::::


----------------------------

<!--  ----------------------------------------- -->
### How to generate the ReadMe file?

There are two recommended ways to generate your own *ReadMe* file: 

- With the submission [**online interface**][vizier-submit-login]:
	- The upload table process generates a *ReadMe* skeleton and the standardized tables, both are required for VizieR.
	- The *ReadMe* file can then be edited online, or downloaded on your computer and edited.
	- Uploading your own *ReadMe* is also an option.


**// TO COMPLETE!!!!**

- With the [cdspydreadme][vizier-cdspyreadme] Python module that generates pre-filled *ReadMe* files for data stored in `CSV`, `votable`, `FITS`, `astropy.Tables`, or `MRT` formats,

![ReadMe Generator Python library Github page (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_cdspyreadme.png){alt="Screenshot: ReadMe Generator Python library Github page, from July 2023"}

The whole *ReadMe* can then be tested with the command line tool [anafile][anafile]. 
But in any case, do your best and the CDS team will make sure that your data is easily understandable and can be re-used and cited by everyone. 
**// True ???**



<!--  ----------------------------------------- -->
<!-- 	Submission interface			-->
<!--  ----------------------------------------- -->
## Data submission (option 1): Online interface

<!--  ----------------------------------------- -->
<!-- 		Step-by-step: submission form	-->
<!--  ----------------------------------------- -->
<!-- https://cdsarc.cds.unistra.fr/vizier.submit/help.html -->
### Submission form (option 1): step-by-step

The first option is to use the online interface available at: [https://cdsarc.cds.unistra.fr/vizier.submit/][vizier-submit-login].
More detailed information on how to use this service can be found on the [VizieR catalogue upload (HELP) page][vizier-submit-data-help].

No account creation is needed. One just needs to create a name for the session, eg. *my_unique_id_2023*.



<!-- Submission form Vizier as iframe -->
<iframe src="https://cdsarc.cds.unistra.fr/vizier.submit/"
title="VizieR catalogue upload webpage"
style="border: 1px solid black; width: 95%; height: 600px; 
overflow: hidden; display: block; "
allowfullscreen="" allow="autoplay" data-external="1"></iframe>

VizieR catalogue upload webpage. 
Note that it is not an image, you can submit your files directly from here.




![VizieR catalogue upload page - start uploading Tables (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_submit_data_interface__step1_tables.png){alt="Screenshot: VizieR Catalogue upload page, start uploading Tables after initiating a session, from June 2023"}


-------

-------



<!--  ----------------------------------------- -->
<!-- 		Step-by-step: FTP		-->
<!--  ----------------------------------------- -->
<!-- https://cdsarc.cds.unistra.fr/vizier.submit/help.html -->

## Data submission (option 2): File Transfer Protocol 

An other option is to submit your data through File Transfer Protocol. 

Since October 2021, FTP uploads requires a login authentification.
A web application is available for authors to obtain a temporary login/password:
[https://cds.unistra.fr/ftp/token/][vizier-ftp-login]
(include the FTP instruction).

<!-- VizieR FTP token as iframe -->
<iframe src="https://cds.unistra.fr/ftp/token/"
title="VizieR FTP token generation webpage"
style="border: 1px solid black; width: 95%; height: 680px; 
overflow: hidden; display: block; "
allowfullscreen="" allow="autoplay" data-external="1"></iframe>

VizieR FTP token generation webpage.
Note that it is not an image, you can already generate a temporary login.



<!--  ----------------------------------------- -->
<!--            Data at CDS                     -->
<!--  ----------------------------------------- -->
## What happens to your data at the CDS? 

Once the data submitted on the CDS servers, some checking procedures are executed to verify the compatibility between the data files and their description. This can lead to interactions with the authors, but we are trying to minimize the level of interaction. 

Once the data are public, they are accessible as plain files in [FTP directories at CDS][ftp-cats] and other participating [data centers][vizier-mirors] (e.g. at [CfA/Harvard (USA)][vizier-at-cfa] or [NOAJ/ADAC (Japan)][vizier-at-noaj]).


![Journey from a publication to EOSC: fourth step of the journey - steps curation & verification](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/lighthouse/step4.svg){alt="Figure -- Summary data journey from a publication to VizieR and then EOSC: fourth step of the journey - step curation and verification of the data, right after - step data published in a refereed paper, step preparation of the data, step submission of the data"}


<!--  ----------------------------------------- -->
<!--            Summary                         -->
<!--  ----------------------------------------- -->

## Summary: Data submission and curation

::::::::::::::::::::::::::::::::::::: keypoints

2 options for data submission:

- Online interface
- File Transfer Protocol

The *ReadMe* file describe your tables:

- This highly standardised file allows reusability and cross matching between catalogs
- No need to build it from scratch

Once the catalogues are submitted, a delay is needed for VizieR curation and validation before full ingestion!

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

