# Delete older Launch Config and AMI 

This script will enable anyone to delete Old Launch Configurations and respective EC2 AMI when new Launch configuration is attached to the Auto Scaling Group. 

We have an automated script in place that creates a new AMI and Launch Configuration and is attached to the Auto Scaling Group, whenever a new deployment is made. This helps us to have latest deployed code on the new AMI, so that when the ASG spawns a new EC2 instance, it will be spawned from the new AMI. This created a lot of old Launch configs and AMI's and AWS allows a maximum of 200 per region. Since its a very crucial recovery feature to spawn new EC2 instance when ASG limit is met, maintaining Launch Configuration below this value is important.

This script enables anyone to delete older Launch Configuarion and AMI based on the Launch Configuration keyword. It allows you to provide retention day which would delete all the Launch Configuration older than 'x' days.

## Executing the script

/bin/bash delete_Launch_Config_and_AMI XXXXXX 5

where *XXXXXX* is the Launch Configuration keyword name
and *5* is the retention date

Above script will delete all the Launch Configuration and associated AMI with name as ***XXXXXX*** and which are older then ***5*** days.

*NOTE*

Make sure to change the aws cli profile_name as required.