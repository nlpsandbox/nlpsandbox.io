<!-- markdownlint-disable-next-line first-line-h1 -->
{row}
{column width=9}

### Introduction

Patient information derived from academic research, health care and clinical trials are off limit for traditional data-to-model benchmarking. Existing barriers include the access to big and sensitive data and the lack of effective framework for assessing the performance and generalizability of NLP Sandbox tools.

The NLP Sandbox adopts a model-to-data architecture to enable developers to evaluate the performance of their tools on public and private datasets. In this framework, the tools submitted for evaluation are pulled by one or more data hosting sites onboarded into the NLP Sandbox benchmarking network. A tool is then evaluated against the private data available at different data hosting sites, that are secure environments fully controlled by partner organizations. Once the evaluation is complete, the performance of the tool is returned by the partner organization to the NLP Sandbox where it is made available to the community in leaderboards. As we continue to evaluate tools, the best performing tools will move to the top of the leaderboards enabling users (e.g. health systems) to identify the best tools for their sites.

![NLP Sandbox Benchmarking Infrastructure]

### Benchmarking Infrastructure

The NLP Sandbox Team has developed a portal benchmarking infrastructure that partner organizations can deploy to cloud or on-premises resources. The infrastructure is fully controlled by the organization and even the NLP Sandbox Team does not have access to it.

Shortly after starting the onboarding process, the NLP Sandbox Team will provide instruction the the partner organization on how to deploy and run the benchmarking infrastructure and register it as a data hosting site of the NLP Sandbox.

Here are some resources that describes the components of the benchmarking infrastructure:

- [nlpsandbox/nlpsandbox-controller]: The NLP Sandbox Controller is responsible for communicating with nlpsandbox.io to pull submitted tools to evaluate and push back their performance once the evaluation is complete. The controller also takes care of the tool evaluation process.
- [nlpsandbox/docker-elk]: [ELK] (Elasticsearch, Logstash, Kibana) is used to centralize the logs of the different services deployed by the partner organization. ELK provides a user-friendly web client that the organization maintainers can access to monitor the health and logs of the tools.
- [nlpsandbox/aws-cloudformation]: The NLP Sandbox Team provides a CloudFormation template to facilitate the deployment of the benchmarking infrastructure to AWS. If your organization prefers using another cloud provider, the NLP Sandbox Team will work with your organization to create a deployment template. It is also possible to deploy the NLP Sandbox infrastructure on on-premises servers owned by your organization.

### Incentives

Please contact us if your organization is interested in:

- benchmarking new or existing types of NLP Sandbox tools and
- enabling the NLP community to benchmark tools on public or private data.

Other incentives include:

- If your organization is looking to deploy an NLP Sandbox tool to its production environment, your organization will be able to identify the tools that best perform on its own data.
- The NLP developers who publish the performance of their tools on your organization dataset(s) will cite your publications that describe the content of the datasets.
- The logo of your organization will be added to the home page of the NLP Sandbox.
- The contribution of your organization will be mentioned in email communications to the NLP community, press releases, and on the NLP Sandbox social media accounts.

### Onboarding

A preview of the onboarding process is given below:

1. Send an email to team@nlpsandbox.io to request additional information about the onboarding process.
2. The NLP Sandbox Team will provide support to enable your organization to deploy the benchmarking infrastructure.
3. The NLP Sandbox Team will provide support on how to prepare the datasets that your organization will use to benchmark the performance of tools.
4. When the data hosting site is ready, the site will be able to pull submitted tools and evaluate their performance on one or more NLP Sandbox tasks.


{column}
{row}

<!-- Images -->

[NLP Sandbox Benchmarking Infrastructure]: https://github.com/nlpsandbox/nlpsandbox-website-synapse/raw/staging/images/nlpsandbox-benchmarking-infrastructure.png

<!-- Links -->

[nlpsandbox/nlpsandbox-controller]: https://github.com/nlpsandbox/nlpsandbox-controller
[nlpsandbox/docker-elk]: https://github.com/nlpsandbox/docker-elk
[nlpsandbox/aws-cloudformation]: https://github.com/nlpsandbox/aws-cloudformation
[ELK]: https://www.elastic.co/what-is/elk-stack
