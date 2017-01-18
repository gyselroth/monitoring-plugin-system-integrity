# Monitoring Plugin: (Debian) System integrity

### Description

This monitoring plugin makes use of debsums to verify the system integrity.
debsums scanns all installed files from deb packages and compares the checksums of the files with 
the checksusms from the deb packages. 

It is actually a better way to scan your os for rootkits or other bad stuff than using 
out-of-date programms like chkrootkit or rkhunter with false-positive alerts.

### Usage
    -e <PATH> Excludes a given path (Recursive) from the check

### Requirements

* debsums

### Install 

Copy check_system_integrity to your plugin folder and create a service/exec in your monitoring engine. 
