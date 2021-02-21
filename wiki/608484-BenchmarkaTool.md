<!-- markdownlint-disable-next-line first-line-h1 -->
{row}
{column width=8}

### Introduction

The previous section of this tutorial guided you through the development of an NLP Tools using the development environment provided by the NLP Sandbox. This page describes how to benchmark the performance of this tool in the NLP Sandbox.

### Push the NLP Tool Docker Image to Synapse

Developers must submit their NLP Tools to the NLP Sandbox as Docker images. The submitted images will then be pulled by the Data Hosting Sites that meet the requirements to evaluate the performance of tools submitted to specific Tasks.

The first step is to push the Docker image of your tool to your Synapse project. Projects created in Synapse can store a virtually unlimited number of private and public images. Start by identifying the Synapse ID of your project. This ID is displayed on the top-left corner of Synapse just below the navigation bar.

![Synapse Project ID]

At the end of the tutorial that you followed to build the Docker image of the [Date Annotator example], you should have been able to start the Date Annotator on your local computer using the command `docker-compose up`. The Docker image `nlpsandbox/date-annotator-example` should now be available in your list of images.

```console
$ docker-compose up
$ docker images
REPOSITORY                          TAG                 IMAGE ID       CREATED          SIZE
nlpsandbox/date-annotator-example   1.0.0               45c362e39b3e   21 seconds ago   359MB
python                              3.9.1-slim-buster   8c84baace4b3   12 days ago      114MB
nginx                               1.19.6-alpine       629df02b47c8   2 months ago     22.3MB
```

Synapse requires Docker images to be named following a specific syntax that inform Synapse on where the image should be stored (Synapse project). An image can be renamed using the command [docker tag].

```console
# syntax: docker.synapse.org/<Your project ID>/<Descriptive name>:<Tag>
$ docker tag nlpsandbox/date-annotator-example:1.0.0 \
    docker.synapse.org/syn24862084/date-annotator-example:1.0.0
$ docker images | grep date
nlpsandbox/date-annotator-example                       1.0.0               45c362e39b3e   16 minutes ago   359MB
docker.synapse.org/syn24862084/date-annotator-example   1.0.0               45c362e39b3e   16 minutes ago   359MB
```

Last step before pushing the image to your Synapse project: you need to logging to the Synapse Docker registry:

```console
$ docker login docker.synapse.org
Authenticating with existing credentials...
Login Succeeded
```

The output of the command should end with `Login Succeeded`.

You can now push the image.

```console
docker push docker.synapse.org/syn24862084/date-annotator-example:1.0.0
```

The image should now be listed under the tab `Docker` of your Synapse project.

### Set the Shring Settings of the Docker Image



{column}
{row}

<!-- Links -->

[Date Annotator example]: https://github.com/nlpsandbox/date-annotator-example
[docker tag]: https://docs.docker.com/engine/reference/commandline/tag/

<!-- Images -->

[Synapse Project ID]: https://github.com/nlpsandbox/nlpsandbox-website-synapse/raw/staging/images/tools/synapse-project-id.png
