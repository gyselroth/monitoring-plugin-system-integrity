# Monitoring Plugin: (Debian) System integrity

### Description

This fairly simple monitoring plugin makes use of debsums to verify the system integrity.
debsums checks all installed files from deb packages and compares the checksums of the files with 
the checksusms from the deb packages. 

It is actually a better way to scan your os for rootkits or other bad stuff than using 
out-of-date programms like chkrootkit or rkhunter with false-positive alerts.

### Usage
    -e <PATH> Excludes a given path (Recursive) from the check

### Requirements

* debsums

### Install 

Copy check_system_integrity to your plugin folder and create a service/exec in your monitoring engine. 
Keep in mind that this plugin needs a long time to execute. Its depends on the size of your system.
In average you should execute this service check once a day with a timeout of 800s.

Note that there are three different timeouts in the (nrpe/icinga2) monitoring eco system:
(Of course you can execute this check using different ways, for example ssh or icinga2 itself)


Monitoring Checkcommand Timeout

    timeout = 8m

NRPE Plugin timeout
   
    vars.nrpe_timeout = 800

NRPE Daemon timeout
    
    command_timeout=800
