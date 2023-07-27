---
title: "Submitting astronomical data"
teaching: 12
exercises: 6
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

- Option 1: If not too bulky, use the submission [**online interface**][vizier-submit-login]
	- The upload will generate a *ReadMe* skeleton file based on your tables and perform a few basic checks.
	- You will need to check and complete this *ReadMe* file. 
	- Alternatively, if you already have created a *ReadMe* file, you can upload it directly along with your tables.
	- In addition to your table, FITS files (spectra or images) for associated data can be uploaded to improve their discoverability via our [dedicated interface Saada/VizieR][vizier-assoc-data].
- Option 2: Use the [**Python cdspyreadme library**][vizier-cdspyreadme] to create the *ReadMe* file and then upload all the tables and other data by [**FTP**][vizier-ftp-login]


<!-- #### Special case: large volumetry -->
The submission web application is an HTTP service and depends of authors network. The process is dedicated for tables size less than 100Mb but accepts tables until ~200Mb. 


<!-- Contact CDS -->
For larger files or any other questions, please contact the VizieR staff: [cats(at)cdsarc.u-strasbg.fr](mailto:cats@cdsarc.u-strasbg.fr).


![Journey from a publication to EOSC: third step of the journey - step submission of the data](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/lighthouse/step2.svg){alt="Figure -- Summary data journey from a publication to VizieR and then EOSC: third step of the journey - step submission of the data, right after - step data published in a refereed paper, step preparation of the data"}




<!--  ----------------------------------------- -->
<!--   ReadMe files                             -->
<!--  ----------------------------------------- -->
## ReadMe file

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
### Full description of the content of the ReadMe file

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
It therefore differs from the **Abstract** which describes the *scientific results* that the author(s) derived from the data. The **Abstract** is simply the one from your refereed paper. 


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
Acknowledgements: Alexander Kopylov <akop(at)sao.ru>
```
:::::::::::::::::::::::::


<!-- ---------------- -->
:::::::::::::::: solution
#### 12. (optional) 'References' header

This section contains the necessary references. [Bibcodes][bibcode] are strongly encouraged, to enable an automatic link to the existing Abstract Services like ADS.

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
	- This *ReadMe* file can then be edited or you can upload your own file.
- With the [cdspydreadme][vizier-cdspyreadme] Python library:
	- This package builds *ReadMe*, standardized tables (in ASCII aligned format) or MRT tables from tables which can be in different formats (`CSV`, `votable`, `FITS`, `astropy.Tables`, or `MRT` formats)
	- The whole *ReadMe* can then be tested with the command line tool [anafile][anafile]. 

![ReadMe Generator Python library Github page (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_cdspyreadme.png){alt="Screenshot: ReadMe Generator Python library Github page, from July 2023"}



<!--  ----------------------------------------- -->
<!-- 		Step-by-step: submission form	-->
<!--  ----------------------------------------- -->
<!-- https://cdsarc.cds.unistra.fr/vizier.submit/help.html -->
## Data submission (option 1): Online interface

The first option is to use the online interface available at: [https://cdsarc.cds.unistra.fr/vizier.submit/][vizier-submit-login].

This web application enables the upload of the data and invites you to fill a *ReadMe* file generated by the application.
The VizieR upload application will create a **temporary** repository containing your tables, associated files (spectra, images, cubes) if any, and the *ReadMe* file.

**However, even after completing all steps, your catalogue will not be readily available in VizieR. Additional work by the VizieR team is needed, including checks and homogenization to our standards, before the catalogue is fully ingested.**

In the following, we show how to upload your data step-by-step. Additional information on how to use this service can be found on the [VizieR catalogue upload (HELP) page][vizier-submit-data-help].


-------

### Start a session

No account creation is needed. One just needs to choose a login for the session, eg. *my_unique_id_2023*.
The login can be reused until the completion of the process but not after submission.

**Note - 1:** Your login is tight to a given IP address.

**Note - 2:** Please contact the VizieR staff: [cats(at)cdsarc.u-strasbg.fr](mailto:cats@cdsarc.u-strasbg.fr) if a modification to a recently submitted upload is needed.

<!-- Submission form Vizier as iframe -->
<iframe src="https://cdsarc.cds.unistra.fr/vizier.submit/"
title="VizieR catalogue upload webpage"
style="border: 1px solid black; width: 95%; height: 600px; 
overflow: hidden; display: block; "
allowfullscreen="" allow="autoplay" data-external="1"></iframe>

VizieR catalogue upload webpage. 
Note that it is not an image, you can submit your files directly from here.


-------

### Upload tables

The VizieR submit service detects automatically the input format.
Please, upload here only the regular tabular data (tables).
More information on the accepted formats can be found in the Chapter [Preparing your data](../section_prepare_data.md).


The upload will generate:

- a *ReadMe* skeleton including the byte-by-byte based on your uploaded tables
- ASCII tables with aligned columns (FORTRAN Format / MRT (Machine Readable Table))


**Note:** Check that all the tables are uploaded at this stage. Adding tables later implies to remove all tables and *ReadMe*.


![VizieR catalogue upload page - step Tables (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_submit_online_interface_july23/step1_tables.png){alt="Screenshot: VizieR Catalogue upload page, start uploading Tables after initiating a session, from June 2023"} 



-------

### Fill the ReadMe

Once the tables uploaded, the next step is to fill the *ReadMe* file. You can:

- Edit online
- Download and complete locally
- Upload your own *ReadMe* 


Then you submit the updated *ReadMe* with the "upload" button:

- This action will check the consistency between the *ReadMe* and your files. 
- The page is refreshed and a report is displayed. This output is the result of the anafile package - see next section.
- **In case of error, the CDS recommends to review the ReadMe (and remove the ReadMe).**
- But, even if you encountered problems, you can still go to the next step.


**Note - 1:** The online mode makes regular backups. You can restore the last version and force the backup.

**Note - 2:** Check that all the tables are uploaded at this stage. Adding tables later implies to remove all tables and *ReadMe*.


![VizieR catalogue upload page - step Readme (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_submit_online_interface_july23/step2_readme.png){alt="Screenshot: VizieR Catalogue upload page, fill the ReadMe file after initiating a session and uploading your tables, from June 2023"} 



-------

### Upload FITS Spectra / Time series

Once the tables and the *ReadMe* are uploaded, you can upload your associated data: spectra and time series.
More information on the accepted formats can be found in the Chapter [Preparing your data](../section_prepare_data.md).

The FITS upload generates a mapping between the spectra FITS header and ObsCore keywords. We strongly encourage you to modify the mapping to better describe your data.

**Note: Although multiple formats are accepted, only FITS files will be indexed and accessible through the [VizieR associated data service][vizier-assoc-data] and through the Virtual Observatory**. 
The other formats will still be accessible through the FTP. 

The uploaded files can be of the following:

- a single FITS file (possibly compressed)
- a collection of independent FITS files gathered into an archive (.tar)
	- Independent means that headers are not similar and each FITS needs a dedicated mapping
- a collection of similar FITS files gathered into an archive (.tar)
	- In that case, we make a unique mapping to describe all resources in the archive (.tar). Be careful, this option is available only if FITS have similar headers.

For each upload, a report is available. **It is recommended to verify the mapping by clicking on the report header.**


![VizieR catalogue upload page - step FITS Spectra(screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_submit_online_interface_july23/step3_fits_spectra.png){alt="Screenshot: VizieR Catalogue upload page, upload associated data: FITS Spectra and Time Series after initiating a session, uploading your tables and filling the ReadMe file, from June 2023"} 



-------

### Upload FITS images

FITS images can also be uploaded in a similar way as the FITS Spectra (see above).
 
More information on the accepted formats can be found in the Chapter [Preparing your data](../section_prepare_data.md).


![VizieR catalogue upload page - step FITS images (Screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_submit_online_interface_july23/step4_fits_images.png){alt="Screenshot: VizieR Catalogue upload page, upload associated data: FITS Images after initiating a session, uploading your tables, filling the ReadMe file and uploading FITS Spectra and Time Series, from June 2023"} 



-------

### Terminate

**This is the last step of your catalogue submission.**

Please, verify that everything is correct before ending your session. Note that you can go back to the current work using the same login until you have submitted this page with the "Yes" button at the end of the page.

**IMPORTANT POINT:** A summary of the files uploaded is available via a temporary link, but **DO NOT USE** this url as it will disappear after publication.

In the last step you can:

- Upload additional files (keeping in mind the accepted formats)
- Add a message to the VizieR staff

Providing an email address is required at that stage. The email will be used if additional information is needed.

**Note:** If a modification to a recently uploaded is needed, please contact the VizieR staff: [cats(at)cdsarc.u-strasbg.fr](mailto:cats@cdsarc.u-strasbg.fr).




![VizieR catalogue upload page - step Validate (Screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/vizier_submit_online_interface_july23/step5_validate.png){alt="Screenshot: VizieR Catalogue upload page, validate your submission after initiating a session, uploading your tables, filling the ReadMe file and uploading FITS Spectra / Time Series and FITS images, from June 2023"} 



<!--  ----------------------------------------- -->
<!-- 		Step-by-step: FTP		-->
<!--  ----------------------------------------- -->
<!-- https://cdsarc.cds.unistra.fr/vizier.submit/help.html -->

## Data submission (option 2): File Transfer Protocol 

An other option is to submit your data through File Transfer Protocol. 
This option is particularly recommended if the *ReadMe* file was created using the [**Python cdspyreadme library**][vizier-cdspyreadme] and for large files.

Since October 2021, FTP uploads requires a login authentification.
A web application is available for authors to obtain a temporary login/password:
[https://cds.unistra.fr/ftp/token/][vizier-ftp-login]. It includes some FTP instructions.


<!-- VizieR FTP token as iframe -->
<iframe src="https://cds.unistra.fr/ftp/token/"
title="VizieR FTP token generation webpage"
style="border: 1px solid black; width: 95%; height: 680px; 
overflow: hidden; display: block; "
allowfullscreen="" allow="autoplay" data-external="1"></iframe>

VizieR FTP token generation webpage.
Note that it is not an image, you can already generate a temporary login.


-------

### Generate a temporary FTP login

The first step is to register to get a temporary login: available for **3 days**.

To do so, the authors need to provide their email address (e.g. *jane.doe(at)astro.fr*) and choose a login (e.g. *paper\_carbon\_jdoe_jul23*).
This unique FTP login (6 characters at least) will be dedicated for the upload of a single catalogue.

On success, a mail is sent to your email address with the FTP login and some instructions.

-------

### Upload to the CDS repository

Your freshly created account is ready and available for **3** days.
You can put your files directly under the repository  (the root ftp directory being dedicated per login).

More information on the accepted data and formats can be found in the Chapter [Preparing your data](../section_prepare_data.md).

Type the following command in a terminal to access the FTP server: `ftp ftp.cds.unistra.fr`.



``` output
Connected to ftp.cds.unistra.fr.
220 Welcome to the CDS FTP service.
Name: paper_carbon_jdoe_jul23
331 Please specify the password.
Password:
230-------------------------------------------------------
230-CDS FTP repository for authors
230-
230- => temporary directoy for user paper_carbon_jdoe_jul23
230-
230-Note for binary upload: 
230-tape "bin" in prompt command to switch in binary mode
230-
230-ftp> bin
230-
230-(create Thu Jul  6 12:09:25 2023)
230-------------------------------------------------------
230 Login successful.
Remote system type is UNIX.
Using binary mode to transfer files.
ftp> 
```

#### How to upload a table?

To upload a table (e.g. *table.dat*), use the command: `put table.dat`.

```output
ftp> put table.dat
local: table.dat remote: table.dat
200 PORT command successful. Consider using PASV.
```


#### Switching to binary mode
 
In case of Binary data, make sure that your session in in binary mode.
This option, is not set by all FTP client -
To force binary mode, use the command `bin` FTP protocol as follow.


``` output
ftp> bin
200 Switching to Binary mode.
```


#### Passive mode
By accessing the FTP server in *passive mode* -- `ftp -p ftp.cds.unistra.fr` --, one can get the directory listing using `ls`.

```output
ftp> ls
227 Entering Passive Mode (130,79,128,14,36,87).
150 Here comes the directory listing.
-rw-r--r--    1 115      120          1570 Jul 06 14:08 ReadMe.txt
-rw-r--r--    1 115      120        259200 Jul 06 14:09 spectra_test.fit
-rw-r--r--    1 115      120             0 Jul 06 14:02 table.dat
226 Directory send OK.
```


-------

### Notify the VizieR team

Once you are done uploading your data (*ReadMe*, tables and any other associated data), you need to **SEND AN E-MAIL** to the VizieR team telling them where you have placed files: [cats(at)cdsarc.u-strasbg.fr](mailto:cats@cdsarc.u-strasbg.fr).



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

![Before: Units as written in original paper (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_1_units_before.png){alt="Screenshot -- Table with wrong units as displayed in paper"}



Our team picked it up and wrote to the author and made the description and unit correction (field *V* from the figure below).

![After: Units corrected in VizieR table (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_1_units_after.png){alt="Screenshot -- VizieR table with units corrected"}

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

![Before: Coordinates as written in original paper (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_2_coordinates_before.png){alt="Screenshot -- Table with wrong coordinates as made available in paper"}


Once the error detected by our team, the positions were then updated, two years after the data ingestion in VizieR.


![After: Coordinates corrected in VizieR table (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_2_coordinates_after.png
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

![Example of names recognized by SIMBAD added to the original table submitted to VizieR (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_3_names.png){alt="Screenshot -- VizieR table with SIMBAD-names added"}

:::::::::::::::::::::::::


<!--  ----------------------------------------- -->
#### Verifications: Example 4 - Odd values

We add mimimum and maximum values of numerical columns. It allows us to detect some oddities and it is helpful also for the astronomer who will validate the catalogue afterwards.

:::::::::::::::: testimonial
#### Min-max values added

![Example of minimum and maximum values added to a ReadMe file (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_4_minmax.png){alt="Screenshot -- VizieR ReadMe file with minimum and maximum values added to the numerical fields"}

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


![Example of missing data retrieved, adding more visibility to the original set (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_5_missing_data.png
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

![Extract of Table A from paper (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_6_missing_key_table1.png){alt="Screenshot -- Table A as displayed in paper"}


![Before: extract of Table B from paper (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_6_missing_key_table2_before.png){alt="Screenshot -- Table B as displayed in paper"}


As there are no common identifier or coordinates repeated in the second table, the only alternative would have been to go through the list of references cited (3rd column of *Table B*) to get the coordinates and identify the object one by one.
Therefore, the CDS team contacted the author to get the names and positions for *Table B* and create a better link between the two tables as displayed below.

![After: extract of Table B as available in VizieR (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_6_missing_key_table2_after.png){alt="Screenshot -- Table B updated as available on VizieR"}


:::::::::::::::::::::::::



<!--  ----------------------------------------- -->
### Errata

As said before, the VizieR database is evolving every day: with new catalogues being added or old ones being updated. 


:::::::::::::::: testimonial
#### Tables updated

In the example below, one table from the original catalogue was updated, to reflect the changes published in an erratum.

![Example of a table updated following erratum publication (screenshot)](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/data_curation_examples/example_7_errata.png){alt="Screenshot -- Table from catalogue updated to be consistent with erratum publication"}

:::::::::::::::::::::::::





<!--  ----------------------------------------- -->
<!--            Data curation at CDS            -->
<!--  ----------------------------------------- -->
## Data available to all

Once the data are public, they are accessible as plain files in [FTP directories at CDS][vizier-catalogue-collection] and other participating [data centers][vizier-mirors] (e.g. at [CfA/Harvard (USA)][vizier-at-cfa] or [NOAJ/ADAC (Japan)][vizier-at-noaj]), as well as all VO compatible services.


![Journey from a publication to EOSC: fourth step of the journey - steps curation & verification](https://raw.githubusercontent.com/cds-astro/a-FAIR-journey-for-astronomical-data/main/episodes/images/lighthouse/step4.svg){alt="Figure -- Summary data journey from a publication to VizieR and then EOSC: fourth step of the journey - step curation and verification of the data, right after - step data published in a refereed paper, step preparation of the data, step submission of the data"}



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

