<a name="home"></a>
  
## I Relecov Biohackathon
## Group 2
Participants: Maria Lara, Erika Kvalem, Alberto Lema & Ivan Bloise

## Tasks

<ul>
  <li><a href="#Development_gisaid_upload.py">Task 1. Development gisaid_upload.py.</a></li>
  <li><a href="#Email_advertisement">Task 2. Email advertisement json_validation.py.</a></li>
  <li><a href="#PipInstallation">Task 3. Pip installation.</a></li>
</ul>


<!-- ************************** SECTION HERE -->

Helps
- [MarkDown cheatsheet](https://www.markdownguide.org/cheat-sheet/)
- [Repository of Relecov-tools](https://github.com/BU-ISCIII/relecov-tools)
- [Lintin Black for VS-Code](https://marcobelo.medium.com/setting-up-python-black-on-visual-studio-code-5318eba4cd00#:~:text=Go%20to%20settings%20in%20your,%E2%80%9D%20and%20select%20%E2%80%9Cblack%E2%80%9D.)

---

<a name="Development_gisaid_upload.py"></a>
### Task 1: Development gisaid_upload.py

Firstly, json schema for GISAID was reviewed and modified accordingly to GISAID specifications. Once gisaid_schema.py was updated, relecov-tools' map module was run in order to test it.

Problems: some non-required fields of gisaid-schema appeared in the resulting json mapped to GISAID, despite they were not present in the processed-json.

A research on how to submit samples to GISAID was perfomed. GISAID has created a command line tool named cli3 Files needed for batch submissions:
- Metadata.csv 
[link](../group2/files/20210222_EpiCoV_BulkUpload_Template.xls)

- Multifasta (ids/headers must match gisaid_virus_name format) i. e.:
> >hCoV-19/Spain/xxxxxx/2022

Functions added to gisaid_upload.py:
- create_multifasta() #create multifasta from single fasta files
- change_headers() #transform ids/headers to GISAID format

  
<!-- ************************** SECTION HERE -->

<a name="Email_advertisement"></a>
### Task 2: Email advertisement json_validation.py

- Use FASTQ files from IonTorrent sequencing technology (PGM and/or S5) from the HERA project as benchmarking to test Viral-Recon. We have access to FASTQ files for ten known samples provided by BU-ISCIII. We want to test:
  <ol>
    <li>The raw FASTQ files into Viral-Recon.</li>
    <li>The uBam files (some sort of raw FASTQ format file from IonTorrent).</li>
    <li>The FASTQ files with some preprocessing filtering (BQ>20).</li>
  </ol>
- Test directly with the FASTQ files provided (if any) into Viral-Recon.
- Set a BaseQuality filter (?) and other possible filters (depending on the noise within the input reads, specially in indels) in the config of Viral-Recon.
- Sarai and Joan provided examples of FASTQ obtained with IonTorrent technologies.

  <p align="right" dir="auto">
   <a href="#home" title="Up">
    <img src="../group4/images/home-icon.png" style="max-width: 100%;">
   </a>
 </p>
  
  
---

<!-- ************************** SECTION HERE -->
 
<a name="PipInstallation"></a>
### Task 3: Pip Installation

- Check if a UBam-to-FASTQ is needed depending on the IonTorrent datasets provided.
- Several outputs are expected: FASTQ (if the user knows how to download files in this format from the sequencing platform), uBAM and BAM.
- We will need to test TMAP and IRMA.

**Tools to preprocess the Ion Torrent FASTQ files in case they are provided as BAM or uBAM**

**How to perform BAM-to-FASTQ**


...





