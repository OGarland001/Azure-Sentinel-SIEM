# Azure-Sentinel-SIEM

## Azure:

Free trial
Try Microsoft Sentinel free for the first 31 days. Microsoft Sentinel can be enabled at no additional cost on an Azure Monitor Log Analytics workspace, subject to the limits stated below.

New workspaces can ingest up to 10GB/day of log data for the first 31-days at no cost. Both Log Analytics data ingestion and Microsoft Sentinel charges are waived during the 31-day trial period. This free trial is subject to a 20 workspace limit per Azure tenant.
Usage beyond these limits will be charged per pricing listed on this page. Charges related to additional capabilities for automation and bring your own machine learning are still applicable during the free trial.

https://azure.microsoft.com/en-ca/pricing/details/microsoft-sentinel/#:~:text=Microsoft%20Sentinel%20can%20be%20enabled,31%2Ddays%20at%20no%20cost.

## The Process:

![image](https://github.com/OGarland001/AWS-Azure-Sentinel-SIEM/assets/90342911/edd5b780-935f-4d33-828c-4313cb9d0cf6)

We are going to open up a VM and turn off all firewall rules (_Unrecommended_), but for the lab it is what we want to do so that the world wide hackers will be able to identify the machine and begin trying to hack into it.

### Azure Account.

### VM Setup.

Create a virtual machine, turn off the external azure firewall and turn off the internal windows firewall for the VM. This will make it very easy to detect and cause more hackers to detect it and try to break into it, but since we are making a honeypot it is good so that we can detect all of the people trying to break into the system.

new firewall config
![New Fire wall config](image.png)

remove everything from this firewall we gotta make it unsafe
![Alt text](image-1.png)

adding these rules to allow anything
![](image-2.png)

Got the VM setup and remooved the windows fire wall, now we are going to need to be viewing the Event Viewer so we can grab our authenication logs.

Each login attempt we are going to use Event Viewer to log each one and then we can grab an IP address from that event then map it to our global map but we gotta an API for that and that is where ipgeolocation comes in.

Loaded in a powershell program that will use the logs and then use the API to geolocate every login attempt so we can monitor.
![Alt text](image-3.png)

### Log repository inside Log Analytics Workspace

### Setup Azure Sentinel

This will allow for us to map the data coming from the logs and place the geolocation we are tracking on the map.
