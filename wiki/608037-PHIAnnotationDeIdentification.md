## Introduction

## Date Annotation

A Date Annotator takes as input a clinical note and outputs a list of predicted
date annotations found in the clinical note.

[![Date Annotator API](https://img.shields.io/badge/OpenAPI-Open_NLP_Task_Specification-plop?color=94398d&labelColor=555555&logoColor=ffffff&style=for-the-badge&logo=openapi-initiative&label=)][date-annotator-api]

[![Date Annotator Leaderboard](https://img.shields.io/badge/OpenAPI-Review_Leaderboard-plop?color=94398d&labelColor=555555&logoColor=ffffff&style=for-the-badge&logo=openapi-initiative&label=)][date-annotator-leaderboard]

Example Tools:

- [nlpsandbox/date-annotator-example] (Python)
- [nlpsandbox/date-annotator-example-java]

Benchmarking:

- Submission queue: `NLP sandbox - Date Annotator`
- Submission quota: 2 submissions / team / week
- Datasets:
    - [2014 i2b2 NLP De-id Challenge Dataset]

## Person Name Annotation

The Person Name Annotator takes as input a clinical note and outputs a list of
predicted person name annotations found in the clinical note.

[![Person Name Annotator API](https://img.shields.io/badge/OpenAPI-Open_NLP_Task_Specification-plop?color=94398d&labelColor=555555&logoColor=ffffff&style=for-the-badge&logo=openapi-initiative&label=)][person-name-annotator-api]

[![Person Name Annotator Leaderboard](https://img.shields.io/badge/OpenAPI-Review_Leaderboard-plop?color=94398d&labelColor=555555&logoColor=ffffff&style=for-the-badge&logo=openapi-initiative&label=)][person-name-annotator-leaderboard]

Example Tools:

- [nlpsandbox/person-name-annotator-example] (Python)

Benchmarking:

- Submission queue: `NLP sandbox - Person Name Annotator`
- Submission quota: 2 submissions / team / week
- Datasets:
    - [2014 i2b2 NLP De-id Challenge Dataset]

## Physical Address Annotation

The Physical Address Annotator takes as input a clinical note and outputs a list
of predicted physical address annotations found in the clinical note.

[![Gitpod](https://img.shields.io/badge/OpenAPI-Open_NLP_Task_Specification-plop?color=94398d&labelColor=555555&logoColor=ffffff&style=for-the-badge&logo=openapi-initiative&label=)][physical-address-annotator-api]

[![Physical Address Annotator Leaderboard](https://img.shields.io/badge/OpenAPI-Review_Leaderboard-plop?color=94398d&labelColor=555555&logoColor=ffffff&style=for-the-badge&logo=openapi-initiative&label=)][physical-address-annotator-leaderboard]

Example Tools:

- [nlpsandbox/physical-address-annotator-example] (Python)

Benchmarking:

- Submission queue: `NLP sandbox - Physical Address Annotator`
- Submission quota: 2 submissions / team / week
- Datasets:
    - [2014 i2b2 NLP De-id Challenge Dataset]

## PHI De-identification

The NLP Sandbox Team is working with the community to identify the specification
of this task.

If you would like to contribute to the development of the specification of this
NLP Task (input and output schemas, datasets, baseline methods):

1. Review the [draft specification of the NLP Sandbox PHI Deidentifier API].
2. Open a ticket or a Pull Request in the GitHub repository
   [nlpsandbox/nlpsandbox-schemas].
3. Join us on the [NLP Sandbox Discord server] and post your question or
   suggestion to the channel `#schemas`.

Target Task opening date: Spring 2020

## Evaluation

### Definitions

**Instance**: The instance of an annotation. For example, "John Smith",
"Children's hospital" are annotation instances.

**Token**: The individual component of an instance that are separated by a
space. From the Person Name annotation instance "John Smith", "John" and "Smith"
are two tokens. From the Address annotation instance "Children's hospital",
"Children's" and "hospital" represent one token each.

**Instance-level evaluation**: The evaluation is performed by comparing
predicted and gold standard annotation instances using two modes:

- **Strict mode**: A point is awarded to the NLP Annotator if the predicted and
   gold standard annotation match perfectly (location of the starting character
   and length of the annotation). If the annotator fails to predict that "Smith"
   is part of the gold standard annotation "John Smith", for example, then no
   point is awarded.
- **Relax mode**: While the location of the starting character of the predicted
   and gold standard annotation must still match, the predicted length of the
   annotation may fall within +- 2 characters of the length of the gold standard
   annotation. This is to account for occurences where a human may have
   annotated a string like "Backer's" while others, sentient NLP Annotator
   included, may consider that the annotation should be limited to "Backer".

**Token-level evaluation**: The evaluation is performed by comparing the tokens
that compose the predicted and gold standard annotation instances. Looking back
at the example where an NLP Annotator captures only "John" from "John Smith",
then it would be partially awarded. To get the entire point, the annotator must
predict "John Smith" or "John" and "Smith".

**Precision**: $\frac{\text{Number of correct annotations
retrieved}}{\text{Total number of annotations retrieved}}$

**Recall**: $\frac{\text{Number of correct annotations retrieved}}{\text{Total
number of correct annotations  retrieved}}$

**F1 score**:  $\frac{precision * recall*2}{precision + recall}$

### Annotation Location Evaluation

This section describes how the Annotators listed on this page are evaluated
regarding their ability to annotate - or detect - entities of interest from the
content (text) of clinical notes. In its simplest form, a `Text Annotation` is
defined by:

- The location of its starting character in the text.
- The length of the annotation (number of characters).

These two properties are documented as part of the NLP Sandbox [TextAnnotation]
schema.

The performance of an annotator to accuratly predict the location of entities of
interest (e.g., dates, person names, etc.) is evaluated by comparing the
predicted [TextAnnotation] objects returned by the annotator to the gold
standard annotations identified by humans.

The performance metrics listed below are reported in the Leaderboards for the
category "Annotation Location":

- `F1 Instance Strict`: F1 score for the instance-level evaluation (strict mode).
- `F1 Instance Relax`: F1 score for the instance-level evaluation (relax mode).
- `F1 Token`: F1 score for the token-level evaluation.

### Annotation Location and Type Evaluation

In addition for being evaluated in the caterogy "Annotation Location", an NLP
Annotator is evaluated in the category "Annotation Location and Type" if

- the NLP task defines a type for the annotation AND
- the NLP Annotator predicts at least one annotation with a type specified AND
- the dataset used to evaluate the annotator includes at least one gold standard
  annotation with a type specified.

List of NLP Tasks that have an annotation type:

- **Physical Address Annotation**: the schema [TextPhysicalAddressAnnotation]
  defines the type property `addressType`.

In this evaluation category, a predicted annotation is correct if 1) the
annotator successfully identify the location of the gold standard annotation
(strict instance-level evaluation) and 2) correctly identify the type of the
annotation.

The performance metrics listed below are reported in the Leaderboards for the
category "Annotation Location and Type":

- `F1 Type`: F1 score for successfully identifying the annotation location and
  type.
- `Recall Type`: Recall used to compute `F1 Type`.
- `Precision Type`: Precision used to compute `F1 Type`.

<!-- Links -->

[date-annotator-api]: https://nlpsandbox.github.io/nlpsandbox-schemas/date-annotator/latest/docs/
[person-name-annotator-api]: https://nlpsandbox.github.io/nlpsandbox-schemas/person-name-annotator/latest/docs/
[physical-address-annotator-api]: https://nlpsandbox.github.io/nlpsandbox-schemas/physical-address-annotator/latest/docs/
[nlpsandbox/date-annotator-example]: https://github.com/nlpsandbox/date-annotator-example
[nlpsandbox/date-annotator-example-java]: https://github.com/nlpsandbox/date-annotator-example-java
[nlpsandbox/person-name-annotator-example]: https://github.com/nlpsandbox/person-name-annotator-example
[nlpsandbox/physical-address-annotator-example]: https://github.com/nlpsandbox/physical-address-annotator-example
[draft specification of the NLP Sandbox PHI Deidentifier API]: https://github.com/nlpsandbox/nlpsandbox-schemas
[nlpsandbox/nlpsandbox-schemas]: https://github.com/nlpsandbox/nlpsandbox-schemas
[NLP Sandbox Discord server]: https://discord.gg/Zb4ymtF
[TextAnnotation]: https://github.com/nlpsandbox/nlpsandbox-schemas/blob/develop/openapi/commons/components/schemas/TextAnnotation.yaml
[TextPhysicalAddressAnnotation]: https://github.com/nlpsandbox/nlpsandbox-schemas/blob/develop/openapi/commons/components/schemas/TextPhysicalAddressAnnotation.yaml
[2014 i2b2 NLP De-id Challenge Dataset]: https://www.synapse.org/#!Synapse:syn22277124/wiki/608223

[date-annotator-leaderboard]: https://www.synapse.org/#!Synapse:syn22277124/wiki/608039
[person-name-annotator-leaderboard]: https://www.synapse.org/#!Synapse:syn22277124/wiki/608040
[physical-address-annotator-leaderboard]: https://www.synapse.org/#!Synapse:syn22277124/wiki/608041
