<!-- markdownlint-disable-next-line first-line-h1 -->
{row}
{column width=12}

### Annotation Location

${preview?entityId=syn26165070}

${synapsetable?query=select id as "Submission Id"%2C createdOn as "CreatedOn"%2C submitterid as Submitter%2C tool%5F%5Fapi%5Fversion as "NLP Sandbox Version"%2C  location%5FF1%5Ftoken%5Fstrict as "i2b2 Score"%2C MCW%5Flocation%5FF1%5Ftoken%5Fstrict as "MCW score"%2C tool%5F%5Fname as "Tool Name"%2C  tool%5F%5Fversion as "Tool Version"%2C tool%5F%5Furl as "Tool URL"%2C tool%5F%5Fdescription as "Tool Description"%2C tool%5F%5Flicense as "License"%2C dockerrepositoryname as "Image"%2C dockerdigest as "Image Digest"%2C dataset%5Fname as "i2b2 dataset"%2C dataset%5Fversion as "i2b2 dataset version"%2C MCW%5Fdataset%5Fname as "MCW dataset name"%2C MCW%5Fdataset%5Fversion as "MCW dataset version" from  syn23747126 where evaluationid %3D9614799 and status %3D %27ACCEPTED%27 and MCW%5Fsubmission%5Fstatus %3D %27SCORED%27&showquery=false}

### Additional Information

- Latest schema version: `1.2.0`
- Latest version of the i2b2 dataset: `i2b2-phi-20210606`
- Latest version of the MCW dataset: `mcwdataset-20210525`
- Score definition: `F1 Score (token level)`

{column}
{row}
