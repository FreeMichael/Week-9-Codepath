# Week-9-Codepath

This week in the Codepath we are creating honeypots on cloud servers. I used the Google Cloud Platform (GCP) for my honepot and admin server for handling the functionality of the honeypot server. To access each of these servers we have to ssh into them through the terminal on the local machine.

>gcloud beta compute firewall-rules create mhn-allow-admin --direction=INGRESS --priority=1000 --network=default --action=ALLOW --rules=tcp:3000,tcp:10000 --source-ranges=0.0.0.0/0 --target-tags=mhn-admin

