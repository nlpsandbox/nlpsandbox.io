## Overview

TBA

## Annotation location and address type

${synapsetable?query=select id as "Submission Id"%2C createdOn as "Created
On"%2C submitterid as Submitter%2C dataset%5Fversion as "Dataset Version"%2C
type%5FF1  as "F1"%2C type%5Frecall as "Recall"%2C type%5Fprecision as
"Precision"%2C dockerrepositoryname as Repository%2C dockerdigest as Digest from
syn23747126 where evaluationid %3D 9614658 and status %3D
%27ACCEPTED%27&showquery=false}

- True Positive: Correct annotation location (Instance Strict) and correct
  physical address type.
- False Positive:
- True Negative:
- False Negative:

## Annotation location

${synapsetable?query=select id as "Submission Id"%2C createdOn as "Created
On"%2C submitterid as Submitter%2C dataset%5Fversion as "Dataset Version"%2C
location%5FF1%5Finstance%5Frelax  as "F1 Instance Relax"%2C
location%5FF1%5Finstance%5Fstrict as "F1 Instance Strict"%2C
location%5FF1%5Ftoken%5Fstrict as "F1 Token Strict"%2C dockerrepositoryname as
Repository%2C dockerdigest as Digest  from  syn23747126 where evaluationid %3D
9614658 and status %3D %27ACCEPTED%27&showquery=false}
