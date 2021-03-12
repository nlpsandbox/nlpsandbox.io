<!-- markdownlint-disable-next-line first-line-h1 -->
{row}
{column width=8}

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

TODO: Add image

Since all the tools submitted to a specific tasks implement the same specification, it is possible to develop clients in different programming languages (e.g. Python, Java, R) that interact with them. Examples of clients include the [NLP Sandbox Python Client] that can interact with any tools submitted to the NLP Sandbox and the [NLP Sandbox PHI Deidentifier] (React web client) that can interact with PHI deidentifier tools.

{column}
{row}

<!-- Images -->

<!-- Links -->

[nlpsandbox/date-annotator-example]: https://github.com/nlpsandbox/date-annotator-example
[docker]: https://www.docker.com/
[NLP Sandbox Python Client]: https://github.com/nlpsandbox/nlpsandbox-client
[NLP Sandbox PHI Deidentifier]: https://github.com/nlpsandbox/phi-deidentifier-app
