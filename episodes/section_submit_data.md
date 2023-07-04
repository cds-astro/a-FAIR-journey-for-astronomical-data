---
title: "Submitting astronomical data"
teaching: 5
exercises: 0
---

:::::::::::::::::::::::::::::::::::::: questions 

- How and where to submit your data?
- Do and don't when submitting data?

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

- Option 1: Use the submission **online interface**
	- The upload will generate a *ReadMe* file based on your tables.
	- Some basic checks on the *ReadMe* and data files are performed. 
	- It also includes FITS ingestion procedure to improve the discoverability of images and spectra.
- Option 2: Use the **Python cdspyreadme library** to create the *ReadMe* file and then upload all the tables and other data by **FTP**


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


:::::::::::::::::::::::::::::::::::::: callout

# Disclaimer
In this section, we give a lot of details (as we are dissecting the contents of the *ReadMe*). It can be overwhelming, but the next section covers the tools that exist to help generating a correct *ReadMe* file. You don't need to build it from scratch!


::::::::::::::::::::::::::::::::::::::


----------------------------

<!-- Blank template -->

The [Standards for Astronomical Catalogues][vizier-readme-std] is a complete description of the standard for *ReadMe* files. 
A typical illustration could be e.g. [J/A+A/382/389/ReadMe][vizier-readme-example]. 

The description file contains severals sections; as a general rule, only **section headers are left flushed, while the text is indented** — with the noticeable exceptions of the title, the file names in the File Summary section, and of Note headers ([section 3.5][vizier-cat-35-lengthy]). No line in this description file can exceed 80 characters; it is moreover suggested to limit the textual parts to 70 characters, such that a conversion to FITS could keep the text as COMMENT cards.


Here is a blank template: 

```
$catalogue                                                      ($author, $date)
================================================================================
$title
    $authors
    $bibcode
================================================================================
Keywords: $keywords

Objects:
    -----------------------------------------
       RA   (2000)   DE    Designation(s)
    -----------------------------------------

Abstract:
  $abstract

Description:
  $description

File Summary:
--------------------------------------------------------------------------------
 FileName    Lrecl   Records    Explanations
--------------------------------------------------------------------------------
$tablesIndex

--------------------------------------------------------------------------------
$bytebybyte

See also:
$seealso

Acknowledgements:

References:
================================================================================
     (prepared by author)
```


----------------------------


The description file contains the following parts:

<!-- ---------------- -->
1. *First line*: catalogue designation, an abbreviated title followed within parenthesis by the last name of the first author, a + sign if there are multiple authors, and the year — this information has to be condensed in a single line of 80 characters or less; 


###### Example: 
```
I/221               The Magellanic Catalogue of Stars - MACS (Tucholke+ 1996)
================================================================================
```


:::::::::::::::::::::::::::::::::::::: callout

# Volume and page numbers 
(**NEEDED????**) 
 
- For papers accepted for publication in A&A -- but not yet published -- these will be added directly at CDS,
- For papers accepted in other journals, it is recommended to send them via email (to [cats(at)cdsarc.u-strasbg.fr](mailto:cats@cdsarc.u-strasbg.fr)) when you get these details.

::::::::::::::::::::::::::::::::::::::


<!-- ---------------- -->
2. Full title(s), authors, and reference(s) of the catalogue. Each title is left-adjusted (no indentation); the line(s) containing the authors' names are indented (at least two blanks), and the bibliographic reference is enclosed between angle brackets. The BibCode is introduced by an equal sign, as a word without embedded blank of exactly 20 characters (with the equal sign).


###### Example: 
```
The Magellanic Catalogue of Stars - MACS
     Tucholke H.-J., de Boer K.S., Seitter W.C.
    <Astron. Astrophys. Suppl. Ser., 119, 91-98 (1996)>
    <The Messenger 81, 20 (1995)>
    =1996A&AS..119...91T 
    =1995Msngr..81...20D
================================================================================
```


<!-- ---------------- -->
3. Three categories of **keywords** can be added:

    	+ *ADC\_Keywords* introduces the list of data-related keywords, out of a controlled set $# TODO: find this set$
They are stricly related to the tabular material collected in the paper.

	+ *Keywords*: introduces the list of keywords as in the printed publication
	+ *Mission\_Name*: for data originated from satellite mission, this header precedes the satellite name.


Whatever the category, multiple keywords are separated by a semicolon (;) or a dash (-) embedded in blanks.


###### Example: 
```
ADC_Keywords: Clusters, galaxy ; Galaxies, photometry ; Photometry, CCD
Keywords: galaxies: clusters - galaxies: elliptical and lenticular, cD -
          cosmology: large-scale structure of Universe
```


<!-- ---------------- -->
4. the **Description** is expected to give the *context of the data*, such as instrumentation or observing conditions. 
It therefore differs from the *Abstract* which describes the *scientific results* that the author(s) derived from the data.


<!-- ---------------- -->
- the **File Summary** describes the files composing the set. Each file should be described by its *filename*, the *length of the longest line* (lrecl), the *number of records* (number of lines), and a *caption* (short title of the file). Lengthy notes can be added if necessary.


<!-- ---------------- -->
- the **Byte-by-byte Description**. There is one per file. This description is in a tabular form, each row describing one field (column) of the data file.
Here is an example:

```
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

This part contains a lot of information

- the *starting* column of the data field
- the *format* of the field as a *fortran-like* format
    + **A***n*      for a character column made of *n* characters;
    + **I***n*      for a column containing an integer number of *n* digits;
    + **F***n.d*    for a column containing a float number of width *n* digits and up to *d* digits in the fractional part;
    + **E***n.d*    for a number using the exponential notation;
- the [units][vizier-cat-32-units] used in the field. **SI** units are strongly encouraged, avoid the CGS units (for instance, use **mW/m2** instead of **ergs/s/cm2**).
- the *label* (heading) of the field, made of a single word (*no embedded blank*); a few [basic conventions][vizier-cat-33-labels] are used for usual parameters (e.g. positions) and related quantities (e.g. mean errors).
- the *explanations* can start with the following special characters related to some important data characteristics:
    + **\***        (the asterisk)  indicating a [lengthy note][vizier-cat-35-lengthy]
    + **[...]**     (square brackets)       indicating *data ranges*
    + **?** (question mark) indicating a possibility of [blank or NULL][vizier-cat-34-optional] (unspecified) values


- the **References**: section contains the citations. Bibcodes are strongly encouraged.
For large sets of references, you can also gather them into a dedicated *reference file* named **refs.dat**.

### How to fill the *ReadMe* file?

There are two ways to fill your own ReadMe file: 

- with the [cdspydreadme][vizier-cdspyreadme] python module that generates pre-filled readme files for data stored in `FITS`, `csv`, `astropy.Tables`, or `MRT` formats,
- manually, by looking at examples and adapting to your own table

$ # TODO: does the submission form offer an other way to generate a readme file? $

The whole *ReadMe* can then be tested with the command line tool [anafile][anafile]. 
But in any case, do your best and the CDS team will make sure that your data is easily understandable and can be re-used and cited by everyone. 


## Submission

<!--  ----------------------------------------- -->
<!-- 		Step-by-step: submission form	-->
<!--  ----------------------------------------- -->
<!-- https://cdsarc.cds.unistra.fr/vizier.submit/help.html -->
### Submission form (option 1): step-by-step

The first option is to use the online interface available at: [https://cdsarc.cds.unistra.fr/vizier.submit/][vizier-submit-login].

No account creation is needed. One just needs to create a name for the session, eg. *my_unique_id_2023*.


<!-- Submission form Vizier as iframe -->
<iframe src="https://cdsarc.cds.unistra.fr/vizier.submit/"
title="VizieR catalogue upload webpage"
style="border: 1px solid black; width: 98%; height: 600px; 
overflow: hidden; display: block; "
allowfullscreen="" allow="autoplay" data-external="1"></iframe>

VizieR catalogue upload webpage. 
Note that it is not an image, you can submit your files directly from here.


More detailed information on how to use this service can be found on the [VizieR catalogue upload (HELP) page][vizier-submit-data-help].


![VizieR catalogue upload page - start uploading Tables (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_submit_data_interface__step1_tables.png){alt="Screenshot: VizieR Catalogue upload page, start uploading Tables after initiating a session, from June 2023"}


-------



<!--  ----------------------------------------- -->
<!-- 		Step-by-step: FTP		-->
<!--  ----------------------------------------- -->
<!-- https://cdsarc.cds.unistra.fr/vizier.submit/help.html -->

### File Transfer Protocol (option 2): step-by-step

An other option is to submit your data through File Transfer Protocol. 

Since October 2021, FTP uploads requires a login authentification.
A web application is available for authors to obtain a temporary login/password:
[https://cds.unistra.fr/ftp/token/][vizier-ftp-login]
(include the FTP instruction).

<!-- VizieR FTP token as iframe -->
<iframe src="https://cds.unistra.fr/ftp/token/"
title="VizieR FTP token generation webpage"
style="border: 1px solid black; width: 98%; height: 680px; 
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

*ReadMe* files are highly standardised to allow reusability and cross matching between catalogs.

Once the catalogues are submitted, a delay is needed for VizieR curation and validation before full ingestion!

::::::::::::::::::::::::::::::::::::::::::::::::


<!--  ----------------------------------------- -->
<!--            Next Chapters                   -->
<!--  ----------------------------------------- -->
## Next chapters

In the next chapters, you will learn what happen to your data once they are fully ingested into VizieR.
 




## Ideas ???

***Other source: https://cdsarc.cds.unistra.fr/vizier.submit/help.html***

***Other ressource: https://cdsarc.cds.unistra.fr/vizier.submit/publication-notes.html#section5***

***Other: https://vizier.cds.unistra.fr/vizier/submit.htx***



<!--  ----------------------------------------- -->
<!-- 		Link references			-->
<!--	==> See links.md file			-->
<!--  ----------------------------------------- -->

