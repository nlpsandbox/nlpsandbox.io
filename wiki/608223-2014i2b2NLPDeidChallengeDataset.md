## **The i2b2 challenge dataset**

2014 i2b2 NLP De-id Challenge aimed at developing automated methods to detect the location and types of sensitive information in clinical notes. [[1]](#1).

### **Annotation types**
2014 i2b2 challenge datasets included clinical notes for 296 diabetic patients drawn from the Research Patient Data Repository of Partners Healthcare. [[2]](#2) [[3]](#3) The challenge organizers annotated the type and location of the sensitive information. The annotations were mostly compliant to Safe Harbor HIPAA standard with 18 categories but also were expanded to include some non-HIPAA identifiers that could potentially leave a footprint for re-identification of patients. e.g. the city where the patient locates.

*Table 1. shows a list of annotation types defined by the 2014 i2b2 challenge with specification on whether the annotations belong to HIPAA PhIs and the existance of the annotations in 2014 i2b2 datasets.*
| PHI Category | Type           | i2b2-PHI | HIPAA-PHI | i2b2 training set | i2b2 evaluation set |
|-|-|-|-|-|-|
| AGE          | AGE            | Yes      | Yes       | Yes               | Yes                 |
| CONTACT      | EMAIL          | Yes      | Yes       | Yes               | Yes                 |
| CONTACT      | FAX            | Yes      | Yes       | Yes               | Yes                 |
| CONTACT      | IPADDR         | Yes      | No        | No                | No                  |
| CONTACT      | PHONE          | Yes      | Yes       | Yes               | Yes                 |
| CONTACT      | URL            | Yes      | No        | Yes               | No                  |
| DATE         | DATE           | Yes      | Yes       | Yes               | Yes                 |
| ID           | ACCOUNT        | Yes      | Yes       | No                | No                  |
| ID           | BIOID          | Yes      | Yes       | Yes               | No                  |
| ID           | DEVICE         | Yes      | Yes       | Yes               | Yes                 |
| ID           | HEALTHPLAN     | Yes      | Yes       | Yes               | No                  |
| ID           | IDNUM          | Yes      | Yes       | Yes               | Yes                 |
| ID           | LICENSE        | Yes      | Yes       | No                | No                  |
| ID           | MEDICALRECORD  | Yes      | Yes       | Yes               | Yes                 |
| ID           | SSN            | Yes      | Yes       | No                | No                  |
| ID           | VEHICLE        | Yes      | Yes       | No                | No                  |
| LOCATION     | CITY           | Yes      | Yes       | Yes               | Yes                 |
| LOCATION     | COUNTRY        | Yes      | No        | Yes               | Yes                 |
| LOCATION     | DEPARTMENT     | Yes      | No        | No                | No                  |
| LOCATION     | HOSPITAL       | Yes      | No        | Yes               | Yes                 |
| LOCATION     | LOCATION-OTHER | Yes      | No        | Yes               | Yes                 |
| LOCATION     | ORGANIZATION   | Yes      | Yes       | Yes               | Yes                 |
| LOCATION     | ROOM           | Yes      | No        | No                | No                  |
| LOCATION     | STATE          | Yes      | No        | Yes               | Yes                 |
| LOCATION     | STREET         | Yes      | Yes       | Yes               | Yes                 |
| LOCATION     | ZIP            | Yes      | Yes       | Yes               | Yes                 |
| NAME         | DOCTOR         | Yes      | No        | Yes               | Yes                 |
| NAME         | PATIENT        | Yes      | Yes       | Yes               | Yes                 |
| NAME         | USERNAME       | Yes      | No        | Yes               | Yes                 |
| OTHER        | OTHER          | Yes      | No        | No                | No                  |
| PROFESSION   | PROFESSION     | Yes      | No        | Yes               | Yes                 |

<br />

### **Dataset Size**
60% of the 2014 i2b2 dataset were released to the public as a training dataset. The remaining 40% of clinical notes were used as goldstandard to evaluate the performance of the de-identification models submitted by participants to the challenge. All the annotated sensitive information was replaced by synthetic surrogates to prevent information leakage. The training and evaluation datasets are available from [https://www.i2b2.org/NLP/](https://www.i2b2.org/NLP/).

*Table 2. shows the number of patients, records and the total number of annotations in the training and evaluation sets of the challenge. The names of the files included in the training and evaluation dataset followed this format: <patient_id>-<record_id>.xml.*

|Dataset|Number of Patients| Number of Records| Number of Annotations|
|-|-|-|-|
|Training|178|790|17405|
|Evaluation|118|514|11462|

#
### **References**
<a id="1">[1]</a>
Stubbs, A., Kotfila, C. & Uzuner, Ö. Automated systems for the de-identification of longitudinal clinical narratives: Overview of 2014 i2b2/UTHealth shared task Track 1. J. Biomed. Inform. 58 Suppl, S11–9 (2015).
<a id="2">[2]</a>
Kumar, V., Stubbs, A., Shaw, S. & Uzuner, Ö. Creation of a new longitudinal corpus of clinical narratives. J. Biomed. Inform. 58 Suppl, S6–S10 (2015).

<a id="3">[3]</a>
Stubbs, A. & Uzuner, Ö. Annotating longitudinal clinical narratives for de-identification: The 2014 i2b2/UTHealth corpus. J. Biomed. Inform. 58 Suppl, S20–9 (2015).