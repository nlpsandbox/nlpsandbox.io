# NLP Sandbox Website

Pages of the NLP Sandbox website hosted on Synapse

## Overview

This repository includes the pages of the [NLP Sandbox website] hosted on
Synapse.org. This repository is used by the [NLP Sandbox Team] to track changes
made to the website pages and continuously deploy (CD) them to Synapse.

Using this reposiotry instead of Synapse wiki editor offers the following
advantages.

- More than one user to edit a page at the same time.
- The community can propose changes using Pull Requests (PR).
- Robust review process.
- The source code of the pages (markdown) is automatically scanned by a linter
  as part of the CI/CD process to improve code quality.
- Faster page edition as it becomes possible to edit multiple pages at once
  (e.g. search and replace).
- A new website can be created based on this GitHub Template, making it easier
  to re-use and deploy new websites.

## How this repository works

The default branch of this repository is named `staging`. When a contribution
is pushed this branch, the webpages are deployed to a Synapse project that we
refer to as the "staging" website. The staging website is used to visualize
the changes in Synapse before deciding to deploy them to a second Synapse
project refered to as the "production" website.




## How to use this repository

### Create a new Synapse website




1. [Create a repository from this template].
2. Create the following GitHub Secrets for your repository
   - `SYNAPSE_USERNAME`
   - `SYNAPSE_API_KEY`
2. In the [CI/CD workflow], update the following environment variables with the
   ID of your staging and production website hosted on Synapse.org.
   - `staging_synapse_project_id`
   - `production_synapse_project_id`

###



## Working with website pages

### Fetch pages from Synapse

The commands below were used to grab the pages of the [NLP Sandbox Staging website]
in markdown format and save them to the directory [wiki].

```
cd wiki
challengeutils pull-wiki syn22277124
```

### Push pages to Synapse

The commands below pushed the pages in [wiki] to [NLP Sandbox Staging website].

```
cd wiki
challengeutils push-wiki syn22277124
```

## Mirroring staging site to production

The command below copies the pages in the staging site to the production site.

```
challengeutils mirror-wiki syn22277124 syn22277123
```


## Contributing

This project is a community effort and lives off your contributions, be it in
the form of bug reports, feature requests, discussions, or fixes and other
code changes.

Before you start to code, we recommend discussing your plans through a
[GitHub issue], especially for more ambitious contributions. This gives other
contributors a chance to point you in the right direction, give you feedback
on your design, and help you find out if someone else is working on a similar
contribution.

## License

[Apache License 2.0]

<!-- Links -->

[NLP Sandbox website]: https://www.synapse.org/#!Synapse:syn22277123
[NLP Sandbox Staging website]: https://www.synapse.org/#!Synapse:syn22277124
[NLP Sandbox Team]: https://github.com/orgs/nlpsandbox/people
[GitHub issue]: https://github.com/nlpsandbox/nlpsandbox-website-synapse/issues/new/choose
[Apache License 2.0]: https://github.com/elixir-cloud-aai/foca/blob/dev/LICENSE
[Create a repository from this template]: https://github.com/nlpsandbox/nlpsandbox-website-synapse/generate
[CI/CD workflow]: .github/workflows/ci.yml