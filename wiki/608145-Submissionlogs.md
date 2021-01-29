### Submission logs

#### Sage Data Hosting Site

* Login to Sage VPN
* Go to Kibana (link and credentials in Sage favorite password manager)
* Click to open side panel menu, under Kibana, click "Discover"
* Click "Open", then select "nlp-submissions"
* Make sure to change the time frame
* if you want to look for a particular submission, you can query the logstash
  by using KQL.  Example - looking for submission 111111

```console
docker.name : /111111
```
