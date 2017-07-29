# geodan-edgeos
EdgeOS scripts and utilities for EdgeMAX routers

## Install
Clone the repository somewhere  
`git clone https://github.com/Geodan/geodan-edgeos`

copy script to Edge router  
`scp geodan-edgeos/scriptname user@router-ip-or-hostname:`

Logon to the router and make script executable  
`chmod +x scriptname`

Run the script on the router  
`./scriptname`

## Scripts
**updateaddressgroup**  
This script reads ip numbers from a free formatted input file and updates the specified firewall address-group by removing ip numbers that do not exist 
in the input file and adding ip numbers that do not exist in the address-group. For instance, the input file can look like something like this (max 1 uncommented ip-number per line):  
```
Mark 1.2.3.4 #temporary!
Mary 5.6.7.8 # used to be 5.6.7.7, comments are ignored
127.0.0.1 localhost
# the next lines are special
Me 8.8.8.8
``` 
usage:  
`updateaddressgroup groupname inputfile`  
where 'groupname' is the name of an existing firewall address-group (if necessary, create an address-group, for example using the GUI)
and 'inputfile' is the name of the file containing ip-addresses
