<!-- markdownlint-disable-next-line first-line-h1 -->
{row}
{column width=9}

### Overview

This section provides dashboards to the person who submit NLP Sandbox tools for evaluation. These dashboards provide information such as the ID of a submission, the progress status, among other information.

### Tips

- The dashboards only show the submissions that you have submitted yourself.
- Please refresh the page if you don't see a submission that you have just submitted.
- You can cancel a submission tthat has not started yet.
- Only submissions that have successfully completed are counted toward your (or your team's) submission quota.
- If you can't figure out why your submission failed, please [open a ticket].
- If your submission has failed, please send a request for your logs.

### Submission Status Definitions

The column `Status` of the dashboard takes the following values: 

Status | Description
---|---
RECEIVED | Your submission has been received
EVALUATION_IN_PROGRESS | Determining internal queue to submit to and evaluation submission on Sage dataset
ACCEPTED | Submitted to different sites for submissions
INVALID | Model either failed to run on Sage data, or prediction file is invalid
REJECTED | Model either failed to run on all internal site's data, or prediction file(s) is invalid

### Evaluation on Other Sites

`{site} Status` column

Status | Description
---|---
[blank] | Waiting to start evaluation
EVALUATION_IN_PROGRESS | Evaluating on site's submission
ACCEPTED | Model created valid prediction file
SCORED | The model successfully scored on the site
INVALID | Model either failed to run on site's data, or prediction file is invalid

<!-- Links -->

[open a ticket]: https://www.synapse.org/#!Synapse:syn22277123/discussion/threadId=7774
