## Sage Data Hosting Site

The SOP below describes how to access the logs of a submission on the Sage Data
Hosting Site given an submission ID.

- Login to Sage VPN
- Go to [NLP Kibana](http://10.23.60.253) (credentials in Sage favorite password
  manager under NLP-ELK stack)
- Click to on the app menu, under `Kibana`, click `Discover`

    <img src="https://github.com/nlpsandbox/nlpsandbox-website-synapse/raw/staging/images/elk/kibana-discover-menu.png" alt="drawing" width="300"/>

- Click `Open`, then search and click `nlp-submissions`

    <img src="https://github.com/nlpsandbox/nlpsandbox-website-synapse/raw/staging/images/elk/kibana-discover-open.png" alt="drawing" width="1200"/>

- Update the time frame if needed

    <img src="https://github.com/nlpsandbox/nlpsandbox-website-synapse/raw/staging/images/elk/kibana-discover-timeframe.png" alt="drawing" width="1200"/>

- In the `Search` bar, enter `*submission_id*` where `submission_id` is the
  Synapse ID of the submission. The asterisk ('*') is required to capture the
  logs of both the submitted Docker container and the controller.

    <img src="https://github.com/nlpsandbox/nlpsandbox-website-synapse/raw/staging/images/elk/kibana-discover-search-by-sub-id.png" alt="drawing" width="1200"/>
