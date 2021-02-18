## Overview

The NLP Sandbox aims to streamline the development and benchmarking of NLP Tools
that are:

- Robust and reliable
- Reproducible
- Re-usable
- Portable
- Cloud-friendly

The sections below describe how to build and benchmark your first NLP Tool using
the NLP Sandbox. But beforehand, let's briefly discuss some of the key aspects
of the design of the NLP Sandbox.

## API (micro-)services vs programs

Most developers are familiar with the development of command-line programs.
Examples of programs include Bash scripts, Python scripts, Java executables,
etc. The behavior of a program is usually defined by command line arguments
and/or the use of a configuration file. One point that characterizes a program
is that after completing its initialization (e.g., detection of GPUs) and
primary task (e.g., processing data), the program shuts down.

Another characteristic of *using* a program - from a user perspective - is that
unless you use a container technology like Docker or Singularity, running a
Python/Java/other program requires that you install a Python/Java/other
environment beforehand.

An Application Programming Interface (API) service is different from a program
on the above two points. A service is a process that is continuously running and
waiting for requests to process. For example, a web service keep listening to
requests from a *clients* (your browser) and returns the requested HTML pages.
Another example are API services that enables a client to create and manage data
remotely using a standard interface (API). Relying on a standard and
documentated API specification enables a service and its clients to be developed
using different programming languages and frameworks.

These two points are among the main reasons why the NLP Sandbox aims to develop
NLP Tools as API services. API services are also inherently cloud-friendly as
they can wait in the cloud (public or private servers) and are ready to answer
requests anytime. Similarly to a web service that respond to million of requests
from different users concurrently, an API service can process multiple requests
in parallel without overhead for the developer of the service. And if your
organization has the required resources, it is always possible to deploy
multiple instances of the same service behind a load balancer that will take
care of distributing the requests among the different instances based on their
CPU load, for example.

## OpenAPI specification

Requiring NLP Sandbox Users to develop NLP Tools as API services instead of
programs is not a decision that we made lightly. We ultimately decided that
the benefits of adopting a design based on the use of APIs outweighed the
risk that we are taking to ask users to develop outside of their comfort zone.
By adopting the [OpenAPI specification] and leveraging the tools developed by the [OpenAPI
community], we actually find development of API services actually faster than
developing a program that offer the same features.

## The Gist of developing an NLP Sandbox Tool

The development of an API service as documented by the NLP Sandbox is outlined
below:

1. Download the OpenAPI specification of an NLP Tool (JSON or YAML document).
2. Generate an initial implementation - also called "stub" - of the NLP tool
   using a single command.
3. Add your code to existing functions.

By the end of Step 2, you have now an API service that you can start -- just
don't expect this service to do anything meaningful as it will return the
message "do some magic!" to all the requests it receives. You can visualize this
behavior by navigating to this [stub of the NLP Sandbox Date Annotator API]
obtained after completing Step 2.

It should be noted that the API service stub generated at Step 2 validates the
data received and returned against the schemas defined in the OpenAPI
specification of the NLP Tool. The API service stub also comes with a web
interface as seen above. Not bad for downloading one JSON file and running one
command!

The complete example implementation of the NLP Sandbox Date Annotator API
achieved after completing Step 3 is available [here].

## Identify the type of tools that you want to develop

The NLP Sandbox Team and community identified the OpenAPI specifications of a
number of NLP Tools. The list of these tool specifications and their example
implementations are documented on the home page of the GitHub repository
[nlpsandbox/nlpsandbox-schemas].

The performance of these tools can then be benchmarked on [nlpsandbox.io]. By
visiting the Leaderboards section of the website and reviewing the performance
of the different NLP tools, a developer could identify the NLP Tasks that are
the most challenging and where his/her contribution could have the strongest
impact.

## Develop your first NLP Sandbox Tool

Follow the instructions given in the README of the GitHub repository
[nlpsandbox/date-annotator-example] to get started with the development
environment designed by the NLP Sandbox Project. By the end of this tutorial,
you will have built a Docker image of our example Date Annotator.

Then head to the Section [Benchmark a Tool] to submit your first NLP tool.





<!-- Links -->

[OpenAPI specification]: https://swagger.io/specification/
[OpenAPI community]: https://www.openapis.org/
<!-- TODO: add link to live dummy API service -->
[stub of the NLP Sandbox Date Annotator API]: tba
<!-- TODO: Add link to live Date Annotator API service -->
[here]: tba
[nlpsandbox/date-annotator-example]: https://github.com/nlpsandbox/date-annotator-example
[nlpsandbox.io]: nlpsandbox.io
[nlpsandbox/nlpsandbox-schemas]: https://github.com/nlpsandbox/nlpsandbox-schemas
[Benchmark a Tool]: #!Synapse:syn22277124/wiki/608484
