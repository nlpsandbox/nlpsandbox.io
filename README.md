# nlpsandbox-website-synapse

Pages of the NLP Sandbox website on Synapse

## Working with website pages

### Fetch pages from Synapse

The commands below were used to grab the pages of the [NLP Sandbox Staging website]
in markdown format and save them to the directory [pages].

```
cd pages
challengeutils download-wiki syn22277124
```

### Push pages to Synapse

The commands below pushed the pages in [pages] to [NLP Sandbox Staging website].

```
cd pages
challengeutils sync-wiki syn22277124 wiki_config.json
```

## Mirroring staging site to production

The command below copies the pages in the staging site to the production site.

```
challengeutils mirror-wiki syn22277124 syn22277123
```

<!-- Links -->

[NLP Sandbox Staging website]: https://www.synapse.org/#!Synapse:syn22277124
[pages](pages)