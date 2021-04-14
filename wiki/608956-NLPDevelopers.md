<!-- markdownlint-disable-next-line first-line-h1 -->
{row}
{column width=9}

### Introduction

The NLP Sandbox aims to streamline the development and benchmarking of NLP Sandbox tools that are:

- Robust and reliable
- Reproducible
- Re-usable
- Portable
- Cloud-friendly

The sections below describe how to build and benchmark your first NLP Sandbox tool using the NLP Sandbox. But beforehand, let's briefly discuss some of the key aspects of the design of the NLP Sandbox.

### API Services vs Programs

Most developers are familiar with the development of command-line programs. Examples of programs include Bash scripts, Python scripts, Java executables, etc. The behavior of a program is usually defined by command line arguments and/or the use of a configuration file. One point that characterizes a program is that after completing its initialization (e.g., detection of GPUs) and primary task (e.g., processing data), the program shuts down. Another characteristic of using a program - from a user perspective - is that unless you use a container technology like Docker or Singularity, running a Python/Java/other program requires that you install a Python/Java/other environment beforehand.

An [Application Programming Interface (API)][ibm-learn-api] service is different from a program on the above two points. A service is a process that is continuously running and waiting for requests to process. For example, a web service keeps listening to the requests from web clients and returns the requested HTML pages. Another example are API services that enables a client to create and manage data remotely using a standard interface (API). Relying on a standard and documentated API specification enables a service and its clients to be developed using different programming languages and frameworks.

These two points are among the main reasons why the NLP Sandbox aims to develop NLP Sandbox tools as API services. API services are also inherently cloud-friendly as they can wait in the cloud (public or private servers) and are ready to answer requests anytime. Similarly to a web service that responds to million of requests from different users concurrently, an API service can process multiple requests in parallel without overhead for the developer of the service. And if your organization has the required resources, it is always possible to deploy multiple instances of the same service behind a load balancer that will take care of distributing the requests among the different instances based on their CPU load, for example.

### The OpenAPI Specification

Requiring NLP Sandbox users to develop NLP Sandbox tools as API services instead of programs is not a decision that we made lightly. We ultimately decided that the benefits of adopting a design based on the use of APIs outweighed the risk that we are taking to ask developers to develop outside of their comfort zone.

By adopting the [OpenAPI specification] and leveraging the tools developed by the [OpenAPI community], we actually find it more efficient to develop an API service than developing a program (see below).

### The Gist of developing an NLP Sandbox Tool

The development of an NLP Sandbox tool as an API service as documented by the NLP Sandbox is outlined in the steps listed below:

1. Download the OpenAPI specification of an NLP Sandbox tool (JSON or YAML document).
2. Generate an initial implementation - also called "stub" - of the NLP Sandbox tool using a single command.
3. Add your code to existing functions.

Steps 1 and 2 can be performed in a single command. For example, a stub for the NLP Sandbox Date Annotator can be generated for different programming languages and frameworks based on the latest OpenAPI specification available for this tool.

![NLP Sandbox Tool Generation]

Stub in Python-Flask:

```console
npx @openapitools/openapi-generator-cli generate -g python-flask -i https://nlpsandbox.github.io/nlpsandbox-schemas/date-annotator/latest/openapi.json
```

Stub in Java-Spring:

```console
npx @openapitools/openapi-generator-cli generate -g java-spring -i https://nlpsandbox.github.io/nlpsandbox-schemas/date-annotator/latest/openapi.json
```

The list of all the programming languages and frameworks supported by the OpenAPI Generator are listed in the GitHub repository [OpenAPITools/openapi-generator].

By the end of Step 2, you now have an API service that you can start -- just don't expect this service to do anything meaningful as it will return the message `do some magic!` to all the requests it receives. You can observe this behavior in this [live example of the Python Date Annotator stub], which you obtain after completing Step 2.

The API service stub generated at Step 2 automatically validates the data received and returned against the schemas defined in the OpenAPI specification of the NLP Sandbox tool, which contributes to the overall robustness and reliability of the tool. The API service stub also comes with a web interface. Not bad for downloading one JSON file and running one command!

The NLP Sandbox Team started from the Python Date Annotator stub and implemented Step 3 in order to provide the users of the NLP Sandbox with a [complete example of the Date Annotator] that can be used to annotate dates in clinical notes -- just don't expect a high performance!

### Incentives

Below is a non-exhaustive list of benefits when using NLP Sandbox:

- Identify challenging NLP Sandbox tasks that would best benefit from your contribution by viewing their leaderboards.
- Increase the visibiity of your NLP Sandbox tools.
- Build portable NLP Sandbox tools that can be deployed in production environments (cloud and on-premises).
- Learn how to craft robuest and reliable using modern software development models and technologies (e.g. using GitHub, CI/CD workflows, Docker).

### Develop your first NLP Sandbox Tool

Please head to the section [How to Participate] and follow the tutorial to develop and benchmark your first NLP Sandbox tool.

{column}
{row}

<!-- Images -->

[NLP Sandbox Tool Generation]: https://github.com/nlpsandbox/nlpsandbox-website-synapse/raw/staging/images/nlpsandbox-server-generation.png

<!-- Links -->

[OpenAPI specification]: https://swagger.io/specification/
[OpenAPI community]: https://www.openapis.org/
[live example of the Python Date Annotator stub]: https://date-annotator-stub.nlpsandbox.io
[complete example of the Date Annotator]: https://date-annotator-example.nlpsandbox.io
[nlpsandbox/date-annotator-example]: https://github.com/nlpsandbox/date-annotator-example
[NLPSandbox.io]: https://nlpsandbox.io
[nlpsandbox/nlpsandbox-schemas]: https://github.com/nlpsandbox/nlpsandbox-schemas
[Benchmark a Tool]: #!Synapse:syn22277124/wiki/608484
[ibm-learn-api]: https://www.ibm.com/cloud/learn/api
[OpenAPITools/openapi-generator]: https://github.com/OpenAPITools/openapi-generator
[How to Participate]: https://www.synapse.org/#!Synapse:syn22277124/wiki/604827
