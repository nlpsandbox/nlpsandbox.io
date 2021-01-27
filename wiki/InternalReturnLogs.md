### Return logs

For Sage Data Hosting Site:

* Login to Sage VPN
* Go to Kibana: http://10.23.60.253/app/home#/ 
    * Password can be found in lastpass in `Shared-NLP Sandbox` named `NLP-ELK stack`.
* Click to open side panel menu, under Kibana, click "Discover"
* Click "Open", and select "nlp-submissions"
* Make sure to change the time frame
* if you want to look for a particular submission, you can query the logstash by using KQL.  Example - looking for submission 111111
```
docker.name : /111111
```