${toc}
#   Evaluation standards
**Instance**: the object being annotated. Like “Jon Smith” , “Children’s hospital”

**Token**: Each individual component separated by space in an instance. In the example of a person object “Jon Smith”,  “Jon Smith” is an instance. “Jon” and “Smith” are two tokens. In the example of an address object,  “Children’s hospital” is an instance. “Children’s” and “hospital” are two tokens.

**Instance level evaluation**: the evaluation is based on instance. In the case of person object “Jon Smith”, if in the submission, only “Jon” is annotated but not Smith, this submission will fail the instance level evaluation for object “Jon Smith”. Instance level evaluation has two levels:  strict and relax. For  an annotation made by participants to count as correct in strict level evaluation, the annotation must have identical contents as the gold standard. In the relax level evaluation for an annotation made by participants, the annotation can have +/-2 characters deviation from the gold standard. In the example of “Children’s hospital”, if the submitted annotation is “Children hospital”, this annotation will fail the strict instance-level evaluation but pass relax instance-level evaluation.

**Token level evaluation**: the evaluation is based on token. In the case of person object “Jon Smith”, if in the submission, only “Jon” is annotated but not Smith, this submission will fail the token level evaluation for object “Smith” but will pass the token level evaluation for object “Jon”. In the token level evaluation, the annotated token has to be exactly identical to gold standard token to be counted as correct. In the case of “Children’s hospital”, if the submitted annotation is “Children hospital”, this annotation will fail the token-level evaluation for token “Children’s”  but pass  the token-level evaluation for token “hospital”.

**Precision**: $\frac{\text{Number of correct annotations  retrieved}}{\text{Total number of annotations retrieved}}$
**Recall**: $\frac{\text{Number of correct annotations retrieved}}{\text{Total number of correct annotations  retrieved}}$
**F1 score**:  $\frac{precision * recall*2}{precision + recall}$

# Challenge Questions
In the NLP sandbox project, we ask challenge participants to identify and annotate sensitive objects of three primary categories: date, person name, physical address. We put below definitions of three categories, expected output format and corresponding evaluation metrics.

## Task 1: Date annotation

**Submission queue**: `NLP sandbox - date`
**Input**: Clinical notes from the i2b2 dataset.
**Output**: Annotated date object(e.g. ‘08/26/20’) in a JSON format, including start position, length of the date object, text content, date format and confidence level.
* (Required) start: the start position of the annotated text in the original note.
* (Required) length: the length of the annotated text in the unit of character.
* (Required) text: the content of the annotated text.
* (Optional) dateFormat: the format of the date object. It’s a general representation of  a given date. e.g.  the dateFormat for 2020/08/26 will be YYYY/MM/DD.
* (Optional) confidence: confidence level for the annotation, return a score with value between 0 and 100.

**Submission Format**: The output needs to be in JSON format. Below is one example. Refer to [data schema](https://github.com/nlpsandbox/nlpsandbox-schemas/blob/develop/openapi/commons/components/schemas/TextDateAnnotation.yaml) for more information.
```json
{
    "textDateAnnotations": [
        {
            "start": 3329,
            "length": 4,
            "text": "2/18",
            "dateFormat": "",
            "confidence": 100
        },
        {
            "start": 39,
            "length": 6,
            "text": "Friday",
            "dateFormat": "",
            "confidence": 100
        }
    ]
}
```
**Performance metrics**: F1 score (token), F1 score (instance), F1 score (date format)
* F1 score (token): token level evaluation.
* F1 score (instance): instance level evaluation. strict/relax
* F1 score (date format): compare the “dateFormat” annotation in submission and gold standard.


## Task 2: Person name annotation

**Submission queue**:  `NLP sandbox - person`
**Input:** Clinical notes from the i2b2 dataset.
 **Output**: Annotated name object (e.g. ‘Jon Smith’) in a JSON format, including start position, length of the name object, text content and confidence level.
* (Required) start: the start position of the annotated text in the original note
* (Required) length: the length of the annotated text in the unit of character.
* (Required) text: the content of the annotated text
* (Optional) confidence: confidence level for the annotation, return a score with value between 0 and 100

**Submission format**: The output needs to be in JSON format. Below is one example. Refer to [data schema](https://github.com/nlpsandbox/nlpsandbox-schemas/blob/develop/openapi/commons/components/schemas/TextPersonNameAnnotation.yaml) for more information.
```json
{
    "textPersonNameAnnotations": [
        {
            "start": 63,
            "length": 14,
            "text": "Yosef Villegas",
            "confidence": 100
        }
    ]
}
```
**Performance metrics**: F1 score (token), F1 score (instance)
* F1 score (token): token level evaluation.
* F1 score (instance): instance level evaluation. strict/relax


## Task 3: Physical address annotation

**Submission queue**: `NLP sandbox - address`
**Input**: Clinical notes from the i2b2 dataset.
**Output**: Annotated address object(e.g. ‘Smith's hospital’) in a JSON format, including start position, length of the address object, text content, addressType and confidence level.
* (Required) start: the start position of the annotated text in the original note.
* (Required) length: the length of the annotated text in the unit of character.
* (Required) text: the content of the annotated text.
* (Optional)addressType: the type of the address object. e.g. city.
* (Optional) confidence: confidence level for the annotation, return a score with value between 0 and 100.

**Submission format**: The output needs to be in JSON format. Below is one example. Refer to [data schema](https://github.com/nlpsandbox/nlpsandbox-schemas/blob/develop/openapi/commons/components/schemas/TextPhysicalAddressAnnotation.yaml) for more information.
```json
{
    "textPhysicalAddressAnnotations": [
        {
            "start": 3598,
            "length": 19,
            "text": "Children’s hospital",
            "addressType": "hospital",
            "confidence": 100
        }
    ]
}
```
**Performance metrics**: F1 score (token), F1 score (instance), F1 score (addressType), F1 score (HIPAA PHI)
* F1 score (token): token level evaluation
* F1 score (instance): instance level evaluation. Strict/relax
* F1 score (addressType): compare the "addressType" in the annotation from submission to gold standard to generate F1 score(addressType)
* F1 score(HIPAA PHI): based on the table  below to infer if  the "addressType" in the annotation is a PHI and generate the F1 score(HIPAA PHI).

| Category | AddressType    | i2b2-PHI | HIPAA-PHI |
|----------|----------------|----------|-----------
| LOCATION | CITY           | Yes      | Yes       |
| LOCATION | COUNTRY        | Yes      | No        |
| LOCATION | DEPARTMENT     | Yes      | No        |
| LOCATION | HOSPITAL       | Yes      | No        |
| LOCATION | LOCATION-OTHER | Yes      | No        |
| LOCATION | ORGANIZATION   | Yes      | Yes       |
| LOCATION | ROOM           | Yes      | No        |
| LOCATION | STATE          | Yes      | No        |
| LOCATION | STREET         | Yes      | Yes       |
| LOCATION | ZIP            | Yes      | Yes       |



** Evaluation example**:
E.g. If a submission is
```JSON
{
    "textPhysicalAddressAnnotations": [
        {
            "start": 3598,
            "length": 4,
            "text": "EHMS",
            "addressType": "hospital"
        },
	    {
            "start": 3598,
            "length": 4,
            "text": "U.S.",
            "addressType": "country"
        },
	    {
            "start": 3598,
            "length": 5,
            "text": "98110",
            "addressType": "zip"
        }
    ]
}
```
 And goldstandard is
```JSON
{
    "textPhysicalAddressAnnotations": [
        {
            "start": 3598,
            "length": 4,
            "text": "EHMS",
            "addressType": "organization"
        },
        {
            "start": 3598,
            "length": 4,
            "text": "U.S.",
            "addressType": "country"
        },
        {
            "start": 3598,
            "length": 5,
            "text": "98110",
            "addressType": "zip"
        }
    ]
]
```
We can convert this example to the table below
|                 | submission   |            | gold standard |            |
|-----------------|--------------|------------|---------------|------------|
|                 | addressType  | HIPAA PHI | addressType   | HIPAA PHI*|
| Object1 "EHMS"  | organization | yes        | hospital      | yes        |
| Object2 "U.S."  | country      | no         | country       | no         |
| Object3 "98110" | zip          | yes        | zip           | yes        |


F1 score (addressType) is generated by comparing submission/addressType column with  gold standard/addressType column. In this example precision: 0.66, recall: 0.66, F1:0.66
F1 score (HIPAA) is generated by comparing submission/HIPAA PHI column with gold standard/HIPAA PHI column.In this example precision: 1, recall: 1,  F1: 1
