<!-- markdownlint-disable-next-line first-line-h1 -->
{row}
{column width=9}

### Introduction

Natural language processing, or NLP, is a technology used in many ways to help computers understand human language. This is particularly impactful in biomedical research, where hospitals have millions of unstructured notes they need to de-identify before sharing with researchers. Manually de-identifying them would put significant strain on healthcare systems, presenting an excellent use case for the application of NLP.

The first series of NLP Sandbox tasks targeted by the NLP Sandbox are the annotation and de-identification of Protected Health Information (PHI) in clinical notes. This first series of tasks have been identified through our collaboration with the first NLP Sandbox partner organization, the [National Center for Data to Health (CD2H)].

This page lists the NLP Sandbox tasks that are open for benchmarking. Each task provides the information required to develop and benchmark an NLP Sandbox tool that meet the specification of the task.

### NLP Sandbox PHI Deidentifier

This example [NLP Sandbox PHI deidentifier] illustrates the modular design of NLP Sandbox tools. This tool depends on an instance of the following NLP Sandbox tools:

- NLP Sandbox Date Annotator
- NLP Sandbox Person Name Annotator
- NLP Sandbox Location Annotator
- NLP Sandbox Contact Annotator
- NLP Sandbox ID Annotator

The example NLP Sandbox PHI Deidentifier aggregates the predictions returned by these annotators, resolves potential annotation conflicts (e.g. when more the annotations predicted by more than one annotator overlap), and de-identifies the annotated PHI in the note.

An instance of the example NLP Sandbox PHI deidentifier is available at [here](https://phi-deidentifier.nlpsandbox.io). This NLP Sanbdox tool can be deployed using Docker using the instruction available in the GitHub repository [nlpsandbox/phi-deidentifier-example].

The list of NLP Sandbox tools this example PHI deidentifier depends on is listed when navigating to the application. Because all the NLP Sandbox date annotators implement the same specification, for instance, it is possible to update the date annotator used by the deidentifier by another implementation, e.g. the best-performing date annotator submitted to [NLPSandbox.io] identified from the leaderboard. Therefore, this example PHI deidentifier becomes more performant as the community submit and benchmark the performance of new NLP Sandbox tools.

<!-- Blue: 0273b3 -->

<!-- [![Date Annotator API](https://img.shields.io/badge/OpenAPI-Open_NLP_Sandbox_PHI_Deidentifier-plop?color=94398d&labelColor=555555&logoColor=ffffff&style=for-the-badge&logo=openapi-initiative&label=)][phi-deidentifier] -->

### Date Annotation

A Date Annotator takes as input a clinical note and outputs a list of predicted date annotations found in the clinical note.

[![Date Annotator API](https://img.shields.io/badge/OpenAPI-Open_NLP_Tool_Specification-plop?color=94398d&labelColor=555555&logoColor=ffffff&style=for-the-badge&logo=openapi-initiative&label=)][date-annotator-api]

[![Date Annotator Leaderboard](https://img.shields.io/badge/OpenAPI-View_Leaderboard-plop?color=94398d&labelColor=555555&logoColor=ffffff&style=for-the-badge&logo=openapi-initiative&label=)][date-annotator-leaderboard]

Example Tools:

- [nlpsandbox/date-annotator-example] (Python)
- [nlpsandbox/date-annotator-example-java]

Benchmarking:

- Submission queue: `NLP sandbox - Date Annotator`
- Submission quota: 1 submission / team / day (resets every day at 00:00:00 UTC)
- AWS instance type: t3.xlarge
- CPU: Container processes spread over 4 cores, max load equivalent to 4 cores at 100% usage
- Memory: Limited to 4 GB
- Runtime: 2 hours
- Disk space: container space (max 10 GB)
- GPU: none
- Datasets:
    - [2014 i2b2 NLP De-id Challenge Dataset]
    - Medical College of Wisconsin (MCW) Dataset

### Person Name Annotation

The Person Name Annotator takes as input a clinical note and outputs a list of predicted person name annotations found in the clinical note.

[![Person Name Annotator API](https://img.shields.io/badge/OpenAPI-Open_NLP_Tool_Specification-plop?color=94398d&labelColor=555555&logoColor=ffffff&style=for-the-badge&logo=openapi-initiative&label=)][person-name-annotator-api]

[![Person Name Annotator Leaderboard](https://img.shields.io/badge/OpenAPI-View_Leaderboard-plop?color=94398d&labelColor=555555&logoColor=ffffff&style=for-the-badge&logo=openapi-initiative&label=)][person-name-annotator-leaderboard]

Example Tools:

- [nlpsandbox/person-name-annotator-example] (Python)

Benchmarking:

- Submission queue: `NLP sandbox - Person Name Annotator`
- Submission quota: 1 submission / team / day (resets every day at 00:00:00 UTC)
- AWS instance type: t3.xlarge
- CPU: Container processes spread over 4 cores, max load equivalent to 4 cores at 100% usage
- Memory: Limited to 4 GB
- Runtime: 2 hours
- Disk space: container space (max 10 GB)
- GPU: none
- Datasets:
    - [2014 i2b2 NLP De-id Challenge Dataset]
    - Medical College of Wisconsin (MCW) Dataset

### Location Annotation

The Location Annotator takes as input a clinical note and outputs a list of predicted location annotations found in the clinical note.

[![Gitpod](https://img.shields.io/badge/OpenAPI-Open_NLP_Tool_Specification-plop?color=94398d&labelColor=555555&logoColor=ffffff&style=for-the-badge&logo=openapi-initiative&label=)][location-annotator-api]

[![Location Annotator Leaderboard](https://img.shields.io/badge/OpenAPI-View_Leaderboard-plop?color=94398d&labelColor=555555&logoColor=ffffff&style=for-the-badge&logo=openapi-initiative&label=)][location-annotator-leaderboard]

Example Tools:

- [nlpsandbox/location-annotator-example] (Python)

Benchmarking:

- Submission queue: `NLP sandbox - Location Annotator`
- Submission quota: 1 submission / team / day (resets every day at 00:00:00 UTC)
- AWS instance type: t3.xlarge
- CPU: Container processes spread over 4 cores, max load equivalent to 4 cores at 100% usage
- Memory: Limited to 4 GB
- Runtime: 2 hours
- Disk space: container space (max 10 GB)
- GPU: none
- Datasets:
    - [2014 i2b2 NLP De-id Challenge Dataset]
    - Medical College of Wisconsin (MCW) Dataset

### Contact Annotation

An NLP Sandbox contact annotator takes as input a clinical note and outputs a list of predicted contact annotations found in the clinical note.

[![Contact Annotator API](https://img.shields.io/badge/OpenAPI-Open_NLP_Tool_Specification-plop?color=94398d&labelColor=555555&logoColor=ffffff&style=for-the-badge&logo=openapi-initiative&label=)][contact-annotator-api]

Example Tools:

- [nlpsandbox/contact-annotator-example] (Python)

Benchmarking:

- Submission queue: `NLP sandbox - Contact Annotator`
- Submission quota: 1 submission / team / day (resets every day at 00:00:00 UTC)
- AWS instance type: t3.xlarge
- CPU: Container processes spread over 4 cores, max load equivalent to 4 cores at 100% usage
- Memory: Limited to 4 GB
- Runtime: 2 hours
- Disk space: container space (max 10 GB)
- GPU: none
- Datasets:
    - [2014 i2b2 NLP De-id Challenge Dataset]
    - Medical College of Wisconsin (MCW) Dataset

### ID Annotation

An NLP Sandbox ID annotator takes as input a clinical note and outputs a list of predicted ID annotations found in the clinical note.

[![ID Annotator API](https://img.shields.io/badge/OpenAPI-Open_NLP_Tool_Specification-plop?color=94398d&labelColor=555555&logoColor=ffffff&style=for-the-badge&logo=openapi-initiative&label=)][id-annotator-api]

Example Tools:

- [nlpsandbox/id-annotator-example] (Python)

Benchmarking:

- Submission queue: `NLP sandbox - ID Annotator`
- Submission quota: 1 submission / team / day (resets every day at 00:00:00 UTC)
- AWS instance type: t3.xlarge
- CPU: Container processes spread over 4 cores, max load equivalent to 4 cores at 100% usage
- Memory: Limited to 4 GB
- Runtime: 2 hours
- Disk space: container space (max 10 GB)
- GPU: none
- Datasets:
    - [2014 i2b2 NLP De-id Challenge Dataset]
    - Medical College of Wisconsin (MCW) Dataset

### PHI De-Identification

The NLP Sandbox Team is still working on identifying the specification of this task.

If you would like to contribute to the development of the specification of this NLP Sandbox task (input and output schemas, datasets, baseline methods):

1. Review the [draft specification of the NLP Sandbox PHI Deidentifier API] (the PHI Deidentifier schemas can be found under `openapi/phi-deidentifier`).
2. Open a ticket or a Pull Request in the GitHub repository [nlpsandbox/nlpsandbox-schemas] and describe your suggestion.
3. Join us on the [NLP Sandbox Discord Server] and post your question or suggestion to the channel `#schemas`.

Target launch date: July 2021

### Evaluation

#### Definitions

**Instance**: The instance of an annotation. For example, "John Smith", "Children's hospital" are annotation instances.

**Token**: The individual component of an instance that are separated by a space. From the Person Name annotation instance "John Smith", "John" and "Smith" are two tokens. From the Location annotation instance "Children's hospital", "Children's" and "hospital" represent one token each.

**Instance-level evaluation**: The evaluation is performed by comparing predicted and gold standard annotation instances using two modes:

- **Strict mode**: A point is awarded to the NLP Annotator if the predicted and gold standard annotation match perfectly (location of the starting character and length of the annotation). If the annotator fails to predict that "Smith" is part of the gold standard annotation "John Smith", for example, then no point is awarded.
- **Relax mode**: While the location of the starting character of the predicted and gold standard annotation must still match, the predicted length of the annotation may fall within +- 2 characters of the length of the gold standard annotation. This is to account for occurences where a human may have annotated a string like "Michael's" while others may consider that the annotation should be limited to "Michael".

**Token-level evaluation**: The evaluation is performed by comparing the tokens that compose the predicted and gold standard annotation instances. Looking back at the example where an NLP Annotator captures only "John" from "John Smith", then it would be partially awarded. To get the entire point, the annotator must predict "John Smith" or "John" and "Smith".

**Precision**:

$$
\begin{align}
\frac{\text{Number of annotations correctly predicted}}{\text{Number of annotations predicted}}
\end{align}
$$

**Recall**:

$$
\begin{align}
\frac{\text{Number of annotations correctly predicted}}{\text{Number of annotations in the gold standard}}
\end{align}
$$

**F1 score**:

$$
\begin{align}
\frac{precision * recall*2}{precision + recall}
\end{align}
$$

#### Annotation Location Evaluation

This section describes how the Annotators listed on this page are evaluated regarding their ability to annotate - or detect - entities of interest from the content (text) of clinical notes. In its simplest form, a `Text Annotation` is defined by:

- The location of its starting character in the text.
- The length of the annotation (number of characters).

These two properties are documented as part of the NLP Sandbox [TextAnnotation] schema.

The performance of an annotator to accuratly predict the location of entities of interest (e.g., dates, person names, etc.) is evaluated by comparing the predicted [TextAnnotation] objects returned by the annotator to the gold standard annotations identified by humans.

The performance metrics listed below are reported in the leaderboards for the category "Annotation Location":

- `F1 Instance Strict`: F1 score for the instance-level evaluation (strict mode).
- `F1 Instance Relax`: F1 score for the instance-level evaluation (relax mode).
- `F1 Token`: F1 score for the token-level evaluation.

#### Annotation Location and Type Evaluation

In addition to being evaluated in the category "Annotation Location", an NLP Annotator is evaluated in the category "Annotation Location and Type" if

- the task defines a type for the annotation AND
- the NLP Annotator predicts at least one annotation with a type specified AND
- the dataset used to evaluate the annotator includes at least one gold standard annotation with a type specified.

List of NLP Sandbox tasks that have an annotation type:

- **Location Annotation**: the schema [TextLocationAnnotation] defines the type property `locationType`.

In this evaluation category, a predicted annotation is correct if 1) the annotator successfully identifies the location of the gold standard annotation (strict instance-level evaluation) and 2) correctly identifies the type of the annotation.

The performance metrics listed below are reported in the leaderboards for the category "Annotation Location and Type":

- `F1 Type`: F1 score for successfully identifying the annotation location and type.
- `Recall Type`: Recall used to compute `F1 Type`.
- `Precision Type`: Precision used to compute `F1 Type`.

{column}
{row}

<!-- Links -->

[National Center for Data to Health (CD2H)]: https://cd2h.org/
[date-annotator-api]: https://nlpsandbox.github.io/nlpsandbox-schemas/date-annotator/latest/docs/
[person-name-annotator-api]: https://nlpsandbox.github.io/nlpsandbox-schemas/person-name-annotator/latest/docs/
[location-annotator-api]: https://nlpsandbox.github.io/nlpsandbox-schemas/location-annotator/latest/docs/
[contact-annotator-api]: https://nlpsandbox.github.io/nlpsandbox-schemas/contact-annotator/latest/docs/
[id-annotator-api]: https://nlpsandbox.github.io/nlpsandbox-schemas/id-annotator/latest/docs/

[nlpsandbox/date-annotator-example]: https://github.com/nlpsandbox/date-annotator-example
[nlpsandbox/date-annotator-example-java]: https://github.com/nlpsandbox/date-annotator-example-java
[nlpsandbox/person-name-annotator-example]: https://github.com/nlpsandbox/person-name-annotator-example
[nlpsandbox/location-annotator-example]: https://github.com/nlpsandbox/location-annotator-example
[draft specification of the NLP Sandbox PHI Deidentifier API]: https://github.com/nlpsandbox/nlpsandbox-schemas
[nlpsandbox/nlpsandbox-schemas]: https://github.com/nlpsandbox/nlpsandbox-schemas
[NLP Sandbox Discord server]: https://discord.gg/Zb4ymtF
[TextAnnotation]: https://github.com/nlpsandbox/nlpsandbox-schemas/blob/main/openapi/commons/components/schemas/TextAnnotation.yaml
[TextLocationAnnotation]: https://github.com/nlpsandbox/nlpsandbox-schemas/blob/main/openapi/commons/components/schemas/TextLocationAnnotation.yaml
[2014 i2b2 NLP De-id Challenge Dataset]: https://www.synapse.org/#!Synapse:syn22277124/wiki/608223
[date-annotator-leaderboard]: https://www.synapse.org/#!Synapse:syn22277124/wiki/608039
[person-name-annotator-leaderboard]: https://www.synapse.org/#!Synapse:syn22277124/wiki/608040
[location-annotator-leaderboard]: https://www.synapse.org/#!Synapse:syn22277124/wiki/608041
[NLP Sandbox PHI Deidentifier]: https://phi-deidentifier.nlpsandbox.io
[PHI Deidentifier]: https://phi-deidentifier.nlpsandbox.io
[phi-deidentifier]: https://phi-deidentifier.nlpsandbox.io
[NLPSandbox.io]: https://nlpsandbox.io
[nlpsandbox/phi-deidentifier-example]: https://github.com/nlpsandbox/phi-deidentifier-example
