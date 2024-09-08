use this as a lookup file to get quick access to 'what the heck port is that number again' area in your brain that just doesn't want to care enough when the internet already has all the answers, so it offloaded the recall responsibility to this here file that you can load into your splunk
make sure you load in the CSV file and then configure a lookup definition
having a lookup definition allows you to lookup multiple values at once
NO LOOKUP DEFINITION:
| lookup serviceports.csv port_num as dest_port proto as protocol OUTPUT description
returns no description
| lookup serviceports.csv port_num as dest_port OUTPUT description
returns multiple descriptions because it doesn't know you are asking about UDP or TCP... or or or...

having a definition allow you to enter
| lookup serviceports port_num as dest_port proto as protocol OUTPUT description
and get a description

ENJOY

PS: This is file was created with some nice regex parsing /etc/services 
