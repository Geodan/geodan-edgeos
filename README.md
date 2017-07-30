# geodan-edgeos
EdgeOS scripts and utilities for EdgeMAX routers

NOTE: THIS IS NOT OFFICIAL UBIQUITI SOFTWARE AND THEREFORE NOT SUPPORTED OR ENDORSED BY Ubiquiti Networks®

## Install
If the router has internet access (replace 'scriptname' by the name of the required script):  
`curl -k -o scriptname https://raw.githubusercontent.com/Geodan/geodan-edgeos/master/scriptname`

else clone the repository somewhere  
`git clone https://github.com/Geodan/geodan-edgeos`

and copy the script to the Edge router  
`scp geodan-edgeos/scriptname user@router-ip-or-hostname:`

Logon to the router and make script executable  
`chmod +x scriptname`

Run the script on the router  
`./scriptname`

## Scripts
**updateaddressgroup**  
This script reads ip numbers from a free formatted input file and updates the specified firewall address-group by removing ip numbers that do not exist 
in the input file and adding ip numbers that do not exist in the address-group. For instance, the input file can look like something like this:  
```
Mark 1.2.3.4 #temporary!
Mary 5.6.7.8 # used to be 5.6.7.7, comments are ignored
127.0.0.1 localhost
# the next lines are special
Google DNS 8.8.8.8 8.8.4.4
``` 
usage:  
`updateaddressgroup groupname inputfile`  
where 'groupname' is the name of an existing firewall address-group (if necessary, create an address-group, for example using the GUI)
and 'inputfile' is the name of the file containing ip-addresses

## Links
About managing a commented whitelist: https://community.ubnt.com/t5/EdgeMAX/Manage-whitelist-of-100-changing-ip-addresses/m-p/2008860#M169949  
About loading spamhaus blacklisted networks using ipset: https://community.ubnt.com/t5/EdgeMAX/Using-spamhaus-lists/td-p/578909


