<!-- markdownlint-disable-next-line first-line-h1 -->
{row}
{column width=12}

### Annotation Location and Address Type

<!-- markdownlint-disable-next-line first-line-h1 -->
${synapsetable?query=select id as "Submission Id"%2C createdOn as "CreatedOn"%2C submitterid as Submitter%2C dataset%5Fname as "Dataset Name"%2Cdataset%5Fversion as "Dataset Version"%2C tool%5F%5Fapi%5Fversion as "Tool Api Version"%2C tool%5F%5Fname as "Tool Name"%2C tool%5F%5Furl as "Tool URL"%2C tool%5F%5Fdescription as "Tool Description"%2C tool%5F%5Flicense as "License"%2C type%5FF1  as "F1 Type"%2C type%5Frecall as "Recall Type"%2C type%5Fprecision as"Precision Type"%2C dockerrepositoryname as Repository%2C dockerdigest as Digest from  syn23747126 where evaluationid %3D 9614658 and status %3D%27ACCEPTED%27 and type%5FF1 is not null&showquery=false}

### Annotation Location

<!-- markdownlint-disable-next-line first-line-h1 -->
${synapsetable?query=select id as "Submission Id"%2C createdOn as "CreatedOn"%2C submitterid as Submitter%2C dataset%5Fname as "Dataset Name"%2C dataset%5Fversion as "Dataset Version"%2C tool%5F%5Fapi%5Fversion as "Tool Api Version"%2C tool%5F%5Fname as "Tool Name"%2C tool%5F%5Furl as "Tool URL"%2C tool%5F%5Fdescription as "Tool Description"%2C tool%5F%5Flicense as "License"%2C location%5FF1%5Finstance%5Frelax  as "F1 Instance Relax"%2Clocation%5FF1%5Finstance%5Fstrict as "F1 Instance Strict"%2Clocation%5FF1%5Ftoken%5Fstrict as "F1 Token Strict"%2C dockerrepositoryname as Repository%2C dockerdigest as Digest  from  syn23747126 where evaluationid %3D9614658 and status %3D %27ACCEPTED%27&showquery=false}

{column}
{row}
