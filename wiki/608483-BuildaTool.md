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
in parallel without overhead for the developer of the service.

TODO: Add image API service vs. program

## Identify the type of tools that you want to develop

The NLP Sandbox