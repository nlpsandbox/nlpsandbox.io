<!-- markdownlint-disable-next-line first-line-h1 -->
{row}
{column width=9}

### Sage Data Hosting Site

The SOP below describes how to access the logs of a submission on the Sage Data Hosting Site given an submission ID.

- Login to Sage VPN.
- Go to [NLP Kibana](http://10.23.60.253) (credentials in Sage favorite password manager under NLP-ELK stack).
- Click to on the app menu, under `Kibana`, click `Discover`.

  ![kibana-discover-menu][kibana-discover-menu]

- Click `Open`, then search and click `nlp-submissions`.

  ![kibana-discover-open][kibana-discover-open]

- Update the time frame if needed.

  ![kibana-discover-timeframe][kibana-discover-timeframe]

- In the `Search` bar, enter `*submission_id*` where `submission_id` is the Synapse ID of the submission. The asterisk ('*') is required to capture the logs of both the submitted Docker container and the controller.

  ![kibana-discover-search-by-sub-id][kibana-discover-search-by-sub-id]

{column}
{row}

<!-- Images -->

[kibana-discover-menu]: https://github.com/nlpsandbox/nlpsandbox-website-synapse/raw/staging/images/elk/kibana-discover-menu.png
[kibana-discover-open]: https://github.com/nlpsandbox/nlpsandbox-website-synapse/raw/staging/images/elk/kibana-discover-open.png
[kibana-discover-timeframe]: https://github.com/nlpsandbox/nlpsandbox-website-synapse/raw/staging/images/elk/kibana-discover-timeframe.png
[kibana-discover-search-by-sub-id]: https://github.com/nlpsandbox/nlpsandbox-website-synapse/raw/staging/images/elk/kibana-discover-search-by-sub-id.png
