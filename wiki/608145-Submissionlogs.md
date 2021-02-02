## Sage Data Hosting Site

The SOP below describes how to access the logs of a submission on the Sage Data
Hosting Site given an submission ID.

- Login to Sage VPN
- Go to [NLP Kibana](http://10.23.60.253) (credentials in Sage favorite password
  manager under NLP-ELK stack)
- Click to on the app menu, under `Kibana`, click `Discover`

    <img src="../images/elk/kibana-discover-menu.png" alt="drawing" width="300"/>

- Click `Open`, then search and click `nlp-submissions`

    <img src="../images/elk/kibana-discover-open.png" alt="drawing" width="1200"/>

- Update the time frame if needed

    <img src="../images/elk/kibana-discover-timeframe.png" alt="drawing" width="1200"/>

- If you want to look for a particular submission, you can query the logstash
  by using Keyword Query Language (KQL). It is important to add the backslash
  at the beginning.  (e.g, looking for submission `9710071`)

    <img src="../images/elk/kibana-discover-search-by-sub-id.png" alt="drawing" width="1200"/>
