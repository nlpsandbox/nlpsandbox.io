<!-- markdownlint-disable-next-line first-line-h1 -->
{row}
{column width=9}

### Introduction

The previous section of this tutorial guided you through the development of an NLP Sandbox tools using the development environment provided by the NLP Sandbox. This page describes how to benchmark the performance of this tool in the NLP Sandbox.

### Push the NLP Sandbox Tool Docker Image to Synapse

Developers must submit their NLP Sandbox tools to the NLP Sandbox as Docker images. The submitted images will then be pulled by the Data Hosting Sites that meet the requirements to evaluate the performance of tools submitted to specific Tasks.

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

Synapse requires Docker images to be named following a specific syntax that tells Synapse which project the image should be added to. An image can be renamed using the command [docker tag].

```console
# syntax: docker.synapse.org/<Your project ID>/<Descriptive name>:<Tag>
$ docker tag nlpsandbox/date-annotator-example:1.0.0 \
    docker.synapse.org/syn24862084/date-annotator-example:1.0.0
$ docker images | grep date
nlpsandbox/date-annotator-example                       1.0.0               45c362e39b3e   16 minutes ago   359MB
docker.synapse.org/syn24862084/date-annotator-example   1.0.0               45c362e39b3e   16 minutes ago   359MB
```

Last step before pushing the image to your Synapse project: you need to log in the Synapse Docker registry. The preferred and most secure way is to use your username and a personal access token (PAT). You can create multiple personal access token (e.g. one token per device) and revoke them at any time. In order to pull and push Docker images to Synapse Docker registry, please visit your [Synapse Personal Access Token page] and create a token that has the *Permissions* `View`, `Download` and `Modify`. Then,

```console
$ docker login docker.synapse.org
Username: <username>
Password: <personal access token>
Login Succeeded
```

The output of the command should end with `Login Succeeded`.

You can now push the image to your Synapse project:

```console
$ docker push docker.synapse.org/syn24862084/date-annotator-example:1.0.0
The push refers to repository [docker.synapse.org/syn24862084/date-annotator-example]
02621ae45008: Pushed
bac6340a9327: Mounted from syn6117378/date-annotator-example-sleep-30
f25b42be85a3: Mounted from syn6117378/date-annotator-example-sleep-30
e85b5191ca65: Pushed
...
9eb82f04c782: Pushed
1.0.0: digest: sha256:57f223d2bc8fafa64d0100217300866aa309150d17c0daff4cc8f68759b44c0c size: 2625
```

The image should now be listed under the tab *Docker* of your Synapse project.

### Docker Image Tag and Digest

The tag of an image is often used to track the version of the program or service it contains. For example, all the tags of the image [nlpsandbox/date-annotation-example] are listed on Docker Hub.

Tags can be deleted and overwritten by the developer of an image. The digest of an image is the only way to uniquely identify it. The digest of an image submitted for evaluation to the NLP Sandbox can be found in the Leaderboard tables.

### Set the Sharing Settings of the Docker Image

By default, the Docker images stored on Synapse inherit the Sharing Settings of the project they belong to as shown in the screenshot below. This behavior is consistent for the [Sharing Settings] of all entities stored on Synapse (files, tables, wikis, etc.).

![Synapse Docker Sharing Settings]

If you want to enable anyone to pull the images of the tools that you submit for evaluation (the image name and digest will be displayed in the Leaderboards), you can create `Local Sharing Settings` for the image.

1. Go to the page of the Docker image on Synapse.
2. `Docker Image Tools` > `Docker Repository Sharing Settings`.

### Submit an NLP Sandbox Tool for Evaluation

Follow the steps listed below to submit the Docker image of your NLP Sandbox tool and benchmark its performance.

1. Go to the page of the Docker image on Synapse.
2. `Docker Image Tools` > `Submit Docker Repository to Challenge`.
3. Select the version of the image to submit.
4. Select the NLP Sandbox submission queue that corresponds to the type of your NLP sandbox tool.
5. Select on behalf of whom you are making the submission.
6. Click on Submit to make the submission.

### Track the Progress of a Submission

You can track the progress of your submissions in the [Submissions Dashboards].

Once your submission has successfully completed, head to the [Leaderboards] to review its performance.

{column}
{row}

<!-- Links -->

[Date Annotator example]: https://github.com/nlpsandbox/date-annotator-example
[docker tag]: https://docs.docker.com/engine/reference/commandline/tag/
[nlpsandbox/date-annotation-example]: https://hub.docker.com/repository/docker/nlpsandbox/date-annotator-example/tags?page=1&ordering=last_updated
[Sharing Settings]: https://docs.synapse.org/articles/managing_teams_for_groups_and_projects.html
[Tasks section]: https://www.synapse.org/#!Synapse:syn22277124/wiki/607935
[Submissions Dashboards]: https://www.synapse.org/#!Synapse:syn22277124/wiki/604838
[Leaderboards]: https://www.synapse.org/#!Synapse:syn22277124/wiki/604828
[Synapse Personal Access Token page]: https://www.synapse.org/#!PersonalAccessTokens:

<!-- Images -->

[Synapse Project ID]: https://github.com/nlpsandbox/nlpsandbox-website-synapse/raw/staging/images/synapse/synapse-project-id.png
[Synapse Docker Sharing Settings]: https://github.com/nlpsandbox/nlpsandbox-website-synapse/raw/staging/images/synapse/synapse-docker-sharing-settings.png
