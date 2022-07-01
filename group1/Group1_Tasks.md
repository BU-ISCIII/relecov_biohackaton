## I Relecov Biohackathon
## Group 1 - Parse laboratory files
Participants:
- Adrián Muñoz Barrera
- Andreu Coello Pelegrín
- Guillermo Gorines Cordero
- Iván Bloise Sánchez
- Víctor García Olivares

---

## Tasks
- Task 1: Parse laboratory files for relecov-tools.
- Task 2: Lab schemas: Analysis and upload.
- Task 3: Script for metadata homogenization.

## Hackathon in days
* [Day 1 (June 29, 2022)](#day-1)
* [Day 2 (June 30, 2022)](#day-2)
* [Day 3 (July 1, 2022)](#day-3)

---

### Day 1:

Generate a JSON file to identify each institution acronym to a specific schema. This file could be found [here](https://github.com/BU-ISCIII/relecov-tools/blob/develop/relecov_tools/schema/institution_to_schema.json).

Created multiple institution schemas to translate original datanames to relecov-tools schema. These schemas contains information about *equivalences* between laboratory names and relecov specific names. Also, contains all *constant* fields. These JSON schemas could be found in:
* [HUGTiP](https://github.com/BU-ISCIII/relecov-tools/blob/develop/relecov_tools/schema/institution_schemas/HUGTiP.json)
* [HUNSC-ITER](https://github.com/BU-ISCIII/relecov-tools/blob/develop/relecov_tools/schema/institution_schemas/HUNSC-ITER.json)
* [ISCIII](https://github.com/BU-ISCIII/relecov-tools/blob/develop/relecov_tools/schema/institution_schemas/ISCIII.json)

---

### Day 2: 

Update of some JSON schemas with more information.

New functions in metadata_homogeneizer.py to translate metadata from laboratories.

Updates in code to improve error-handling.

Added log functions, to generate more informative error and warning messages.

Fix errors in code.

---

### Day 3:

Added new functionality to metadata_homogeneizer.py to handle outer fields in the metadata conversion schemas.

Fix errors in code.

Create this README for Group 1 in order to summarize completed tasks during the Hackathon.
