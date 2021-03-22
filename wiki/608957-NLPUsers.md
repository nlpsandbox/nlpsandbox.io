<!-- markdownlint-disable-next-line first-line-h1 -->
{row}
{column width=9}

### Introduction

The NLP Sandbox enables prospective users (e.g. health systems) to identify the best tools for their sites. As we continue to evaluate tools, the best performing tools will move to the top of the leaderboards.

The NLP Sandbox aims to provide NLP users with production-ready tools that have the following properties:

- Robust and reliable
- Reproducible
- Re-usable
- Portable
- Cloud-friendly

One approach taken by this project is the promotion of coding standard that helps developers write high quality, maintainable, portable, and robust code. For each task, the NLP Sandbox Team provides one or more examples of tools in individual GitHub repositories (e.g. [nlpsandbox/date-annotator-example]). These examples implements many best practices and comes with completed CI/CD workflow that validate the code hygiene (using linters) and run unit/integration tests each time that the developer contributes to the tool.

The adoption of the OpenAPI standard to describe data schemas and tool input and output specifications is a key element of the design of the NLP Sandbox that contributes to the development of production-ready tools. Relying on the OpenAPI specification enables the development of API services (tools) that are cloud-friendly. The tools benchmarked in the NLP Sandbox can then be deployed to the cloud environment of your organization or on your own computer. You only need to have [Docker] installed to deploy a tool.

![NLP Sandbox Clients]

Since all the tools submitted to a specific tasks implement the same specification, it is possible to develop clients in different programming languages (e.g. Python, Java, R) that interact with them. Examples of clients include the [NLP Sandbox Python Client] that can interact with any tools submitted to the NLP Sandbox and the [NLP Sandbox PHI Deidentifier] (React web client) that can interact with PHI deidentifier tools.

### Incentives

Below is a non-exhaustive list of benefits when using NLP Sandbox:

- Easily identify the best-performing tool from the leaderboards.
- The tool that you use is the tool that has been benchmarked.
- Develop your own client (web clients, notebooks, programs) using the programming language/framework of your choice or use a client developed by the community.
- Because all the tools submitted to a given NLP Sandbox task implements the same OpenAPI specification (for a given specification version), you can easily swap one tool for another.

### Deploying an NLP Sandbox tool

This section provides the steps to perform to deploy the [NLP Sandbox Date Annotator Example] on your computer. Once deployed, you will be able to use your browser to automatically annotate dates in clinical notes.

Prerequisites:

1. [Install Git].
2. Install Docker Engine.
    - [Docker Desktop for Mac (macOS)]
    - [Docker Desktop for Windows]
    - [Docker Server for Linux distributions]
3. [Install Docker Compose].

Deploy the date annotator (tool):

1. Clone the GitHub repository [nlpsandbox/date-annotator-example].
2. Open a terminal, navigate to the folder of the repository.
3. Start the date annotator with the command `docker-compose up -d`.
    - When you no longer need the date annotator, stop it with `docker-compose down`.

Annotate dates in clinical notes using the web client (Swagger UI).

- Get information about the tool: [http://localhost/tool]
- Annotate dates in clinical notes: [http://localhost/ui]
    1. Click on the green endpoint *POST /textDateAnnotations*.
    2. Click on *Try it out*.
    3. Under *Request body*, edit the example clinical note specified in the field `text` or leave it as it is.
    4. Click on *Execute* to run the date annotation tool.

![Date Annotator Example UI Try It Out]

### Deploying Submitted Tools

The performance of NLP Sandbox tools submitted for evaluation is visible in leaderboards. For example, the performance of the submitted date annotators are visible in the [Date Annotator Leaderboard]. The metrics used to evaluate the performance of submissions are defined where the task is described (see Tasks).

Each leaderboard include two columns that provide information on how to deploy a given submission:

- *Docker Repository*: Name of the Docker repository of the submitted tool
- *Docker Digest*: Identifier used to uniquely identify a version of a tool

After identifying the tool that you want to deploy based on the information displayed in the leaderboard, write down its `Docker Repository` and `Docker Digest`. For example, the values for the current version of the date annotator example provided are:

- Docker Repository: `docker.synapse.org/syn22277124/date-annotator-example`
- Docker Digest: `sha256:3a7ea297c19a531576c920b85f43dbb9d2a36c0471bce4a2c7d89033b9a51f76`

> Tip: Triple click on the value of a leaderboard cell to select its content before copying it to your clipboard.

In the previous section, you have cloned the GitHub repository of the example date annotator provided by the NLP Sandbox Team. Use your favorite text editor to open the file `docker-compose.yml`:

```yaml
version: "3.8"

services:
  date-annotator:
    image: nlpsandbox/date-annotator-example:1.0.1
    build:
      context: server
      dockerfile: Dockerfile
    container_name: date-annotator
    networks:
      - nlp-sandbox-internal

  nginx:
    image: nginx:1.19.6-alpine
    container_name: nginx
    restart: always
    environment:
      - TOOL_HOST=date-annotator
      - TOOL_PORT=8080
    volumes:
      - ./nginx/nginx.conf:/etc/nginx/nginx.conf:ro
      - ./nginx/templates:/etc/nginx/templates:ro
    networks:
      - nlp-sandbox
      - nlp-sandbox-internal
    ports:
      - "80:80"
    depends_on:
      - date-annotator

networks:
  nlp-sandbox:
  nlp-sandbox-internal:
    internal: true
```

In order to use the tool that you have identified instead of the example tool, replace the line

> `image: nlpsandbox/date-annotator-example:1.0.1`

by

> `image: <Docker Repository>@<Docker Digest>`

Finally,

- Login to the Synapse Docker registry with `docker login docker.synapse.org`.
- Start the tool with the command `docker-compose up -d`.

Note that the team who submits a tool for evaluation can change the the sharing permission of its submissions at any time. This means that a tool listed in a leaderboard is not necessarily publicly available. If Docker fails to pull the docker image with the message "denied: access forbidden", you could try to reach out to the team to ask permission to access the tool. The contact information of the team is visible in the leaderboards.

{column}
{row}

<!-- Images -->
[NLP Sandbox Clients]: https://github.com/nlpsandbox/nlpsandbox-website-synapse/raw/staging/images/nlpsandbox-clients.png
[Date Annotator Example UI Try It Out]: https://github.com/nlpsandbox/nlpsandbox-website-synapse/raw/staging/images/tools/date-annotator-example-ui-try-it-out.png

<!-- Links -->

[nlpsandbox/date-annotator-example]: https://github.com/nlpsandbox/date-annotator-example
[docker]: https://www.docker.com/
[NLP Sandbox Python Client]: https://github.com/nlpsandbox/nlpsandbox-client
[NLP Sandbox PHI Deidentifier]: https://github.com/nlpsandbox/phi-deidentifier-app
[NLP Sandbox Date Annotator Example]: https://github.com/nlpsandbox/date-annotator-example
[Install Git]: https://www.atlassian.com/git/tutorials/install-git
[Docker Desktop for Mac (macOS)]: https://docs.docker.com/docker-for-mac/install/
[Docker Desktop for Windows]: https://docs.docker.com/docker-for-windows/install/
[Docker Server for Linux distributions]: https://docs.docker.com/engine/install/#server
[Install Docker Compose]: https://docs.docker.com/compose/install/
[Date Annotator Leaderboard]: https://www.synapse.org/#!Synapse:syn22277124/wiki/608039
[Tasks]: https://www.synapse.org/#!Synapse:syn22277124/wiki/607935
[http://localhost/tool]: http://localhost/tool
[http://localhost/ui]: http://localhost/ui
