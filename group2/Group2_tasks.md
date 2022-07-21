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



  <p align="right" dir="auto">
   <a href="#home" title="Up">
    <img src="../group4/images/home-icon.png" style="max-width: 100%;">
   </a>
 </p>
  
  
---

<!-- ************************** SECTION HERE -->
 
<a name="PipInstallation"></a>
### Task 3: Pip Installation





...





