Dockerized submissions may add a layer of complexity for challenge participants. As Challenge Organizers, we will do our best in supporting participants throughout the Challenge. Here are some tips to help you in troubleshooting your submission:

${toc}

## **Debug locally**
If you haven't yet, check the log file of the invalid submission, which may help pinpoint the error(s) that is causing the submission to fail. Some common errors are:

* forgetting to copy or install a needed dependency into the image, e.g. scripts, packages, modules, etc.
* attempting to read an input file that is not available. Check [**Data**](#!Synapse:syn22277124/wiki/604826) to review which input files are available to your containers.
* writing to a directory that is not writable, e.g. `/input/`.

You can also locally test-run your container by using the `docker run` command and the available training data as the model's input.  The basic syntax will be:

```
docker run --network none -v $PWD/training/:/input/:ro -v $PWD/output/:/output/ docker.synapse.org/<Your project ID>/<Repo name>:<Tag>
```
where:
* `--network none` disables all network connections to the container (emulating the same behavior as seen in the submission queues)
* `-v $PWD/training/:/input/:ro` is the mounted volume of input files with read-only permissions. More specifically, `$PWD/training/` is the directory on **your local machine** to be mounted into the container (i.e. the training data), `/input/` is the location where the mounted volume will be made available in the container, and `ro` is the permissions granted for the mounted volume. Read-only permissions should be specified as this will emulate the same behavior as seen in the submission queues.<br/><br/>
* `-v $PWD/output/:/output/` is the mounted volume of output files (read-write by default). More specifically, `$PWD/output/` is the directory on **your local machine** where the container's output files will be located, and `/output/` is the location where the model's output will be created in.<br/><br/>
* `docker.synapse.org/<Your project ID>/<Repo name>:<Tag>` is your Docker image (with `<Tag>` being optional).

## **Use available resources**
If you are new to Docker, refer to the [**Docker Submission**](#!Synapse:syn22277124/wiki/604834) page that has been created for this Challenge. Please refrain from asking the Organizers general Docker-related questions and refer instead to Google, StackOverflow, and [**Docker docs**](https://docs.docker.com/get-started/).

We also highly encourage using the [**Discussion forum**](#!Synapse:syn22277124/discussion/default) to get and share information with the other Challenge participants.

## **When to contact the Organizers**
The Challenge Organizers are responsible for preventing/fixing issues related to data. The Organizers will also provide support in the case where participants wrote code that works with the provided training data but fails with the evaluation data.  If you come across any of these errors, please let us know as soon as possible in the [**Discussion forum**](#!Synapse:syn22277124/discussion/default).

---
[< Back to: **Rules & Resources**](#!Synapse:syn22277124/wiki/604831)
