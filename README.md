# Bulker Educational Malware
## ! For Educational Uses Only !

### Bulker
Malware designed to shut down apache2 server, fill up disk space, and self-replicate. 
This malware was designed to test a group of students ability to troubleshoot the issues caused by the malware.

### Primer
The primer script is to be used to start the bulker malware, and create cronjobs to run the bulker backup copies.
Before using primer:

    
    mv bulker /var/mail/.aws-ses && chmod 511 /var/mail/.aws-ses
    
    
If you wish to have primer deleted after bulker execution, hide the primer script by doing:

    mv primer /var/mail/.aws-ec2 && chmod 511 /var/mail/.aws-ec2
    
The bulker malware will look to see if the primer script is located there, and if it is found, it will delete it.

### Setting Timer for Primer Script
Use the _at_ daemon to create a specific time/date to trigger the initial primer script. Make sure to set _at_ job **as root**!

    at 14:00 030322
    bash /var/mail/.aws-ec2
