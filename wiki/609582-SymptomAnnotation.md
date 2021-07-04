<!-- markdownlint-disable-next-line first-line-h1 -->
{row}
{column width=9}

### Introduction

The fast spread of the emerging infectious coronavirus disease-2019 (COVID-19), caused by severe acute respiratory syndrome coronavirus 2 (SARS-CoV-2), led to a worldwide pandemic with high morbidity and mortality rates<sup>[1][1]</sup>. This guideline describes the specific types of information that should be annotated for detecting essential concepts in COVID-19 including signs and symptoms. For indication keywords, the corresponding attributes should be also annotated (details are in the Attributes section). This annotation guideline was developed in collaboration with the Coronavirus Infectious Disease Ontology (CIDO) team<sup>[2][2]</sup>.

This NLP Sandbox task is organized by Sijia Liu and Hongfang Liu at [Mayo Clinic].

### Pre-NLP Sandbox resources

The annotation guideline can be found at [N3C NLP Subgroup wiki].

The following signs and symptoms were collected from CDC<sup>[3][3]</sup> and Mayo Clinic website<sup>[4][4]</sup> as well as literature review<sup>[4][4],[5][5]</sup>.

### COVID Symptom Annotation (launching end of July)

An NLP Sandbox COVID symptom annotator takes as input a clinical note and outputs a list of predicted COVID symptom annotations found in the clinical note.

[![COVID Symptom Annotator API](https://img.shields.io/badge/OpenAPI-Open_NLP_Tool_Specification-plop?color=94398d&labelColor=555555&logoColor=ffffff&style=for-the-badge&logo=openapi-initiative&label=)][covid-symptom-annotator-api]

Example Tools:

- [nlpsandbox/covid-symptom-annotator-example] (Python)

Benchmarking:

- Submission queue: `NLP sandbox - COVID Symptom Annotator`
- Submission quota: 1 submission / team / day (resets every day at 00:00:00 UTC)
- AWS instance type: t3.xlarge
- CPU: Container processes spread over 4 cores, max load equivalent to 4 cores at 100% usage
- Memory: Limited to 4 GB
- Runtime: 2 hours
- Disk space: container space (max 10 GB)
- GPU: none
- Datasets:
    - Mayo Clinic Dataset

### Reference

1. [He, Y., Yu, H., Ong, E. et al. CIDO, a community-based ontology for coronavirus disease knowledge and data integration, sharing, and analysis. Sci Data 7, 181 (2020).][1]
2. [https://www.cdc.gov/coronavirus/2019-ncov/symptoms-testing/symptoms.html][2]
3. [https://www.mayoclinic.org/diseases-conditions/coronavirus/symptoms-causes/syc-20479963][3]
4. [Wang, D. et al. Clinical Characteristics of 138 Hospitalized Patients With 2019 Novel Coronavirus-Infected Pneumonia in Wuhan, China. JAMA, doi:10.1001/jama.2020.1585 (2020).][4]
5. [Wang, F.-S. & Zhang, C. What to do next to control the 2019-nCoV epidemic? The Lancet 395, 391-393, doi:10.1016/s0140-6736(20)30300-7 (2020).][5]

{column} {row}


<!-- Images -->

<!-- Links -->

[1]: https://doi.org/10.1038/s41597-020-0523-6
[2]: https://www.cdc.gov/coronavirus/2019-ncov/symptoms-testing/symptoms.html
[3]: https://www.mayoclinic.org/diseases-conditions/coronavirus/symptoms-causes/syc-20479963
[4]: https://doi.org/10.1001/jama.2020.1585
[5]: https://doi.org/10.1016/s0140-6736(20)30300-7
[N3C NLP Subgroup wiki]: https://github.com/OHNLP/N3C-NLP-Documentation/wiki
[nlpsandbox/covid-symptom-annotator-example]: https://github.com/nlpsandbox/covid-symptom-annotator-example
[covid-symptom-annotator-api]: https://nlpsandbox.github.io/nlpsandbox-schemas/covid-symptom-annotator/latest/docs/
[Mayo Clinic]: https://www.mayoclinic.org/
