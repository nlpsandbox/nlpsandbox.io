<!-- markdownlint-disable-next-line first-line-h1 -->
{row}
{column width=12}

<!-- ### Annotation Location and Type

${synapsetable?query=select id as "Submission Id"%2C createdOn as "CreatedOn"%2C submitterid as Submitter%2C tool%5F%5Fapi%5Fversion as "NLP Sandbox Version"%2C  type%5FF1 as "i2b2 Score"%2C MCW%5Ftype%5FF1 as "MCW Score"%2C tool%5F%5Fname as "Tool Name"%2C  tool%5F%5Fversion as "Tool Version"%2C tool%5F%5Furl as "Tool URL"%2C tool%5F%5Fdescription as "Tool Description"%2C tool%5F%5Flicense as "License"%2C dockerrepositoryname as "Image"%2C dockerdigest as "Image Digest"%2C dataset%5Fname as "i2b2 dataset"%2C dataset%5Fversion as "i2b2 dataset version"%2C MCW%5Fdataset%5Fname as "MCW dataset name"%2C MCW%5Fdataset%5Fversion  as "MCW dataset version" from  syn23747126 where evaluationid %3D 9614658 and status %3D%27ACCEPTED%27 and type%5FF1 is not null and MCW%5Fsubmission%5Fstatus %3D %27SCORED%27&showquery=false} -->

### Annotation Location

${preview?entityId=syn26165072}

${synapsetable?query=select id as "Submission Id"%2C createdOn as "CreatedOn"%2C submitterid as Submitter%2C tool%5F%5Fapi%5Fversion as "NLP Sandbox Version"%2C  location%5FF1%5Ftoken%5Fstrict as "i2b2 Score"%2C MCW%5Flocation%5FF1%5Ftoken%5Fstrict as "MCW score"%2C tool%5F%5Fname as "Tool Name"%2C  tool%5F%5Fversion as "Tool Version"%2C tool%5F%5Furl as "Tool URL"%2C tool%5F%5Fdescription as "Tool Description"%2C tool%5F%5Flicense as "License"%2C dockerrepositoryname as "Image"%2C dockerdigest as "Image Digest"%2C dataset%5Fname as "i2b2 dataset"%2C dataset%5Fversion as "i2b2 dataset version"%2C MCW%5Fdataset%5Fname as "MCW dataset name"%2C MCW%5Fdataset%5Fversion  as "MCW dataset version" from  syn23747126 where evaluationid %3D9614658 and status %3D %27ACCEPTED%27 and MCW%5Fsubmission%5Fstatus %3D %27SCORED%27&showquery=false}

### Additional Information

- Latest NLP Sandbox schema version: `1.2.0`
- Latest i2b2 dataset: `i2b2-phi-20210606`
- Latest MCW dataset: `mcw-phi-20210608`
- Score definition: `F1 score (token level)`

{column}
{row}
