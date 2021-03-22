<!-- markdownlint-disable-next-line first-line-h1 -->
{row}
{column width=9}

### Introduction

This page discusses the 2014 i2b2 NLP De-id Challenge, which was created with the goal of developing automated methods to detect the location and types of sensitive information in clinical notes<sup>[1][1]</sup>.

### Annotation Types

The 2014 i2b2 challenge datasets included clinical notes for 296 diabetic patients drawn from the Research Patient Data Repository of Partners Healthcare<sup>[2][2],[3][3]</sup>. The challenge organizers manually annotated the type and location of the sensitive information. The annotations were mostly compliant to Safe Harbor HIPAA standard with 18 categories but also were expanded to include some non-HIPAA identifiers that could potentially leave a footprint for re-identification of patients (see **Table 1**).

---

**Table 1**. List of all the annotation types defined by the authors of the 2014 i2b2 NLP De-identification Challenge for their dataset. The column `i2b2-PHI` lists all the identifiers that the organizers of the challenge recommend de-identifying. The column `HIPAA-PHI` only lists the identifiers that are recognized by HIPAA. The columns `i2b2 training set` and `i2b2 evaluation set` show whether the training and/or evaluation set of the 2014 i2b2 NLP De-identification Challenge include a specific `i2b2-PHI` identifiers.

|PHI Category| Type|i2b2-PHI|HIPAA-PHI|i2b2 training set|i2b2 evaluation set|
|-|-|-|-|-|-|
| AGE| AGE| Yes      | Yes | Yes | Yes|
| CONTACT | EMAIL          | Yes      | Yes       | Yes               | Yes |
| CONTACT | FAX            | Yes      | Yes       | Yes               | Yes|
| CONTACT | IPADDR         | Yes      | No        | No                | No|
| CONTACT | PHONE          | Yes      | Yes       | Yes               | Yes|
| CONTACT | URL            | Yes      | No        | Yes               | No |
| DATE    | DATE           | Yes      | Yes       | Yes               | Yes|
| ID      | ACCOUNT        | Yes      | Yes       | No                | No|
| ID      | BIOID          | Yes      | Yes       | Yes               | No|
| ID      | DEVICE         | Yes      | Yes       | Yes               | Yes |
| ID      | HEALTHPLAN     | Yes      | Yes       | Yes               | No |
| ID      | IDNUM          | Yes      | Yes       | Yes               | Yes |
| ID      | LICENSE        | Yes      | Yes       | No                | No|
| ID      | MEDICALRECORD  | Yes      | Yes       | Yes               | Yes |
| ID      | SSN            | Yes      | Yes       | No                | No|
| ID      | VEHICLE        | Yes      | Yes       | No                | No|
| LOCATION| CITY           | Yes      | Yes       | Yes               | Yes|
| LOCATION| COUNTRY        | Yes      | No        | Yes               | Yes |
| LOCATION| DEPARTMENT     | Yes      | No        | No                | No|
| LOCATION     | HOSPITAL       | Yes      | No        | Yes  | Yes|
| LOCATION     | LOCATION-OTHER | Yes      | No        | Yes  | Yes|
| LOCATION     | ORGANIZATION   | Yes      | Yes       | Yes  | Yes|
| LOCATION     | ROOM           | Yes      | No        | No   | No|
| LOCATION     | STATE          | Yes      | No        | Yes | Yes|
| LOCATION     | STREET         | Yes      | Yes       | Yes | Yes|
| LOCATION     | ZIP            | Yes      | Yes       | Yes  | Yes|
| NAME         | DOCTOR         | Yes      | No        | Yes  | Yes|
| NAME         | PATIENT        | Yes      | Yes       | Yes | Yes|
| NAME         | USERNAME       | Yes      | No        | Yes | Yes|
| OTHER        | OTHER          | Yes      | No        | No| No |
| PROFESSION   | PROFESSION     | Yes      | No        | Yes | Yes|

### Dataset Size

60% of the 2014 i2b2 dataset were released to the public as a training dataset. The remaining 40% of clinical notes were used as a gold standard to evaluate the performance of the de-identification models submitted by participants to the challenge (see **Table 2**). All the annotated sensitive information was replaced by synthetic surrogates to prevent information leakage. The training and evaluation datasets are available from [this page](i2b2-dataset-dl).

**Table 2**. shows the number of patients, records and the total number of annotations in the training and evaluation sets of the challenge. The names of the files included in the training and evaluation dataset followed this format: `<patient_id>-<record_id>.xml`

|Dataset|Number of Patients| Number of Records| Number of Annotations|
|-|-|-|-|
|Training|178|790|17,405|
|Evaluation|118|514|11,462|

### i2b2 Annotation Names in the NLP Sandbox

In an effort to harmonize the annotation type of multiple dataset, the NLP Sandbox Schemas may use different names for the above annotations. Please refer to the [PHI Annotation & De-Identification] task page for more information about the schemas of the annotations requested by the NLP Sandbox.

### References

1. [Stubbs, A., Kotfila, C. & Uzuner, Ö. Automated systems for the de-identification of longitudinal clinical narratives: Overview of 2014 i2b2/UTHealth shared task Track 1. J. Biomed. Inform. 58 Suppl, S11–9 (2015).][1]
2. [Kumar, V., Stubbs, A., Shaw, S. & Uzuner, Ö. Creation of a new longitudinal corpus of clinical narratives. J. Biomed. Inform. 58 Suppl, S6–S10 (2015).][2]
3. [Stubbs, A. & Uzuner, Ö. Annotating longitudinal clinical narratives for de-identification: The 2014 i2b2/UTHealth corpus. J. Biomed. Inform. 58 Suppl, S20–9 (2015).][3]

{column}
{row}

<!-- Links -->

[1]: https://dx.doi.org/10.1016%2Fj.jbi.2015.06.007
[2]: https://doi.org/10.1016/j.jbi.2015.09.018
[3]: https://doi.org/10.1016/j.jbi.2015.07.020
[i2b2-dataset-dl]: https://www.i2b2.org/NLP/
[PHI Annotation & De-Identification]: https://www.synapse.org/#!Synapse:syn22277124/wiki/607935
