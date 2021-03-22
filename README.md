# NLPSandbox.io

Pages of the NLP Sandbox website hosted on Synapse

## Overview

This repository includes the pages of the [NLP Sandbox website] hosted on
Synapse.org. This repository is used by the [NLP Sandbox Team] to track changes
made to the website pages and continuously deploy (CD) them to Synapse.

Using this repository instead of Synapse wiki editor offers the following
advantages.

- More than one user to edit a page at the same time.
- The community can propose changes using Pull Requests (PR).
- Robust review process.
- The source code of the pages (markdown) is automatically scanned by a linter
  as part of the CI/CD process to improve code quality.
- Faster page editing as it becomes possible to edit multiple pages at once
  (e.g. search and replace).
- A new website can be created based on this GitHub Template, making it easier
  to re-use and deploy new websites.

## How to use this repository

This repository relies on two Synapse projects:

- Production site (e.g. [NLP Sandbox website])
- Staging site

We recommend configuring repositories created from this template to stick to the
following workflow:

- create a fork from the `staging` branch and make all edits/commits in that
  fork
- submit a PR from the fork into `staging`
- request one or more reviewers to accept the changes
- once approved, merge the changes into `staging` (this will trigger the
  deployment to the staging site)

After reviewing the pages on the staging site, a release of this GitHub
repository can be created to mirror the content of the staging site to the
production site.

### Create a new Synapse website

Login to synapse.org and create two Synapse projects, for example named

- `{Project name}`
- `{Project name} - staging`

Navigate to the staging site and create the structure of the pages under the
tab "Wiki" using the tools `Wiki Tools > Add Wiki Subpage` and
`Wiki Tools > Edit Wiki Page Order`. Then reproduce the same structure of pages
in the production site.

Then,

1. [Create a GitHub repository from this template].
2. Add the following GitHub Secrets to your repository to specify the
   credentials that the CI/CD workflow will use to push pages to the staging
   and production sites.
   - `SYNAPSE_USERNAME`
   - `SYNAPSE_API_KEY`
3. In the CI/CD workflow (*.github/workflows/ci.yml*), update the environment
   variables listed below with the ID of your staging and production website
   hosted on Synapse.org.
   - `staging_synapse_project_id`
   - `production_synapse_project_id`
4. Go into the `wiki` folder of this repository, remove the existing markdown
   files, then pull the pages of the staging site previously created using the
   python client [challengeutils].

        pip install challengeutils
        challengeutils pull-wiki staging_project_id

That's it! Your repository can now be used to edit and deploy pages to your
staging and production websites on Synapse.

### Adding, deleting and ordering pages

This repository can not be used to create, delete and order pages on a Synapse
website, as well as change the title of pages. We are expecting to address
these limitations in a future release of the Python client [challengeutils].

Meanwhile, the solution consists in performing the above actions in Synapse,
then update this repository so that it captures the changes made. This can be
done by running the command below in the *wiki* folder before committing the
changes. Mardkown files that are no longer needed must be deleted manually.

    challengeutils pull-wiki staging_project_id

## Acknowledgments

This repository uses the Python client [challengeutils] to interact with
Synapse. The development of this client is led by [Tom Yu] and other members of
[Sage Bionetworks].

## Contributing

Thinking about contributing to this project? Get started by reading our
[Contributor Guide](CONTRIBUTING.md).

## License

[Apache License 2.0]

<!-- Links -->

[NLP Sandbox website]: https://www.synapse.org/#!Synapse:syn22277123
[NLP Sandbox Staging website]: https://www.synapse.org/#!Synapse:syn22277124
[NLP Sandbox Team]: https://github.com/orgs/nlpsandbox/people
[GitHub issue]: https://github.com/nlpsandbox/nlpsandbox-website-synapse/issues/new/choose
[Apache License 2.0]: https://github.com/nlpsandbox/nlpsandbox-website-synapse/blob/staging/LICENSE
[Create a GitHub repository from this template]: https://github.com/nlpsandbox/nlpsandbox-website-synapse/generate
[CI/CD workflow]: .github/workflows/ci.yml
[challengeutils]: https://github.com/Sage-Bionetworks/challengeutils
[Tom Yu]: https://github.com/thomasyu888
[Sage Bionetworks]: https://sagebionetworks.org/
