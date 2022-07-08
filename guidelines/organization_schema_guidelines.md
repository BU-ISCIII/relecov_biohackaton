# Schema guidelines
Welcome to this guideline gathering all needed instructions to create the schema for the normalization of the lab metadata for the relecov platform.
As all of you already know, GISAID and ENA require certain structure on the metadata for the upload to be successful. 

However, not all labs provide valid metadata structures, so we have worked on a method to normalize your lab metadata to be ENA and GISAID-friendly. 

This method allows the correct generation of the metadata for ENA and GISAID, and is based in the following principles:

* There are **equivalences** between the fields your own lab's metadata, and the required fields.
* Some fields are **constant** for your organization.

With this in mind, the _homogeneizer_ module of the [relecov-tools](https://github.com/BU-ISCIII/relecov-tools) allows the change from your average metadata file, to a relecov-ready metadata file, rather than having to modify your file manually. To do this, two resources are needed:

### Your organization schema
In order to generate the relecov-normalized metadata from your own lab metadata, it is necessary to vinculate the fields in both, and to inform the module of which files are going to be constant. This is achieved through your **institution schema**, which is a JSON file containing all the equivalences and constants that will transform your very lab metadata into the final metadata. The structure for this file can be found in the [template schema](https://github.com/BU-ISCIII/relecov-tools/blob/develop/relecov_tools/schema/institution_schemas/template.json) available in the [relecov-tools](https://github.com/BU-ISCIII/relecov-tools) repository.

Take into consideration that the _key_, the first value in each couple, will always correspond to the field in the _final metadata sheet_).

As you may see, three categories can be found within this file:

* **Equivalence**: this category contains the fields that directly correlate your initial metadata with the required metadata structure. 

To set an easy **example**, lets say the needed metadata field is "Sample ID given by the submitting laboratory". This information is present in your lab's metadata, but with a different name, for instance "ID de muestra". In such case, include the following in your institution metadata:

```
{
    "equivalences" : { "Sample ID given by the submitting laboratory": "ID de muestra" }
}

```
**NOTE**: Don't worry too much about the format here, this is just an example! 

It is perfectly possible that one of your fields corresponds to more than one field, just like it happens in here:

```
{
    "equivalences" : {
        "Sample ID given by the submitting laboratory": "ID de muestra",
        "Sample ID given in the microbiology lab": "ID de muestra",
        "Sample ID given for sequencing": "ID de muestra"
        }
}
```

* **Constant**: this category contains those fields that are unvariable for your institution. 

As an easy **example**, for some institution the author(s) is always the same (the author is always, lets say, "Edward Jenner and Florence Nightingale"), or the extraction protocol remains unchanged (it is always "Protocol01"). Given that case, the institution metadata should contain:

```
{
    "constants" : {
        "Authors": "Edward Jenner and Florence Nightingale",
        "Rna Extraction Protocol": "Protocol01"
        }
}
```
Of course, sometimes the lab does not provide, or is not able to provide, with certain fields. In such situations, stating that field as a constant is the way to go:

If, on top of the above example, we had a category such as "Host Gender", that we have no access to, we can set it as a constant with an empty value:

```
{
    "constants" : {
        "Authors": "Edward Jenner and Florence Nightingale",
        "Rna Extraction Protocol": "Protocol01",
        "Host Gender": ""
        }
}
```

Note that this can be named with "NA" or similars as well. We will try and modify them afterwards so they have the same format.

* **Outer**: this category contains those fields that, though available from your institution, are not placed in the same file as the rest of the metadata you provided.
  
As the last **example**, for some institution, the field "FIELD" is placed in another file you sent along with the rest of the metadata.



Note that the process is complex.



However, how does the module detect which schema to use? This is thanks to the next resource

* Presence of your organization name in the

As of July 2022, the fields required are the following:

in order to upload your samples and metadata to ENA and GISAID, 
