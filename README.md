# Week-9-Codepath

This week in the Codepath we are creating honeypots on cloud servers. I used the Google Cloud Platform (GCP) for my honepot and admin server for handling the functionality of the honeypot server. To access each of these servers we have to ssh into them through the terminal on the local machine.

>gcloud beta compute firewall-rules create mhn-allow-admin --direction=INGRESS --priority=1000 --network=default --action=ALLOW --rules=tcp:3000,tcp:10000 --source-ranges=0.0.0.0/0 --target-tags=mhn-admin

By running the command above it allows ingress traffic through the ports between 3000 and 10000, which is needed to make the honeypot vulnerable. In regular day to day business, networks should practice the safe habit of disabling any unused ports, but since were trying to get attacked we open this wide range up.

Once the directions for setting up the mhn-admin vm is complete we ssh in and install git to download the github repo that will be used in setting up our honeypot. We exit the terminal to get out of the ssh connection and back to the local directory, then we set up the honeypot firewall rules and create the honeypot vm just like we did for the mhn-admin vm.

We then can go to the GCP site and look at the attacks that have already began to come in. Along with GCP to keep track of intrusions, we also have a .json file that logs all the attacks that have occurred.

Looking at this .json file we find that these commonly targeted ports were attacked:

```
Port 21 "FTP" --------------------- # Attacks: 7
Port 23 "Telnet" ------------------ # Attacks: 354
Port 25 "SMTP" -------------------- # Attacks: 7
Port 53 "DNS" --------------------- # Attacks: 3
Port 110 "POP3" ------------------- # Attacks: 3
Port 135 "Windows RPC" ------------ # Attacks: 1
Port 137-139 "Windows NetBIOS ----- # Attacks: 32
Port 1433 "Microsoft SQL Server---- # Attacks: 17
```
Having these logs are crucial especially in a business environment. This is some small server set up, imagine a large corporation that has a target on its back; one can only imagine how many attacks these people would have to deal with.


