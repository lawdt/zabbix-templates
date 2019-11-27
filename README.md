# Zabbix templates
This repository contains zabbix templates for this software and hardware. detailed info listed bellow by directory name.
- Cisco Prime\
- cisco ucs\
- hp ipmi drives discovery\
- ipmi hp bl460c g8\
- ipmi hp DL360 G5\
- ipmi hp DL360 G6\
- ipmi hp DL360p G8\
- ipmi hp DL360p G9\
- ipmi hp DL380p G9 without Drives\
- Nec PNMSj\
- SNMP Sun M5000 xscf\
- Sun blade 2000\
- Sun enterprise T2000 server\
- Sun M4000 prtdiag\
- Sun Ultra 80\
- Sun v440\
- Sun v890\
- Veritas disks discovery on Solaris Sparc\
- ProximVision NMS\
- Junos Space\
- cisco UCS snmp\

##Cisco Prime
This is a simple zabbix template for monitoring Cisco Prime Central components of Cisco Prime Central Network Management system v.6.5 and upper.
Monitored components (different templates):
Cisco Prime Fault management
Cisco Prime Gateway
Cisco Prime Portal
Cisco Prime Provisioning
Cisco Prime Unit
Installation instructions:
1. Copy files from "Config files and scripts" directory to nodes:
- "pp" directory to prime provisioning node (first edit PP version in config)
- "unit" directory to cisco prime unit nodes
- "all systems" directory - copy zabbix config and custom scripts to all nodes.
2. Attach Templates to Cisco Prime Central nodes
3. Edit {$DB_PASSWORD} macros value on Cisco Prime Portal

##cisco ucs
Template for monitoring IPMI sensors for Cisco UCS servers hardware
tested on C220M3
please disable absend HDD and unsupported items after some time.
sensors and triggers:
cpu temperature
DDR modules status
HDD status
LED fan status
overal leds status
Power modules status
other temperature sensors
storage status

## hp ipmi drives discovery
This is simple Template to discover Hard Disk Drives on HP servers by ipmi interface trough iLO This is useful if you have many HP servers with different count of disk drives. In this case you can use my HP servers IPMI templates with excluded HDD sensors. Just Attach Two templates: One for Server Hardware, and one for Disk drives. My HP IPMI Templates with no-HDD option located here: https://share.zabbix.com/owner/lawdt
to use this Template you must do this steps:
configure zabbix server with ipmi support end enable ipmi pollers (see zabbix documentation)
Correcly configure ipmi interface on nodes in zabbix web interface (also see zabbix documentation)
install ipmitool on zabbix server
install python on zabbix server
install python modules: argparse,sys,subprocess,re,json (see python documentation)
copy script to externalscripts directory on zabbix server (see ExternalScripts parameter in zabbix_server.conf)
Import Template to zabbix
Add templates to nodes
Define macroses {$ILO_IP}, {$ILO_USER}, {$ILO_PASSWORD} on node or template level.
Check zabbix server logs if something wrong on debug level 4.

##ipmi hp bl460c g8
simple template to monitor IPMI sensors for HP blade server BL460G8

##ipmi hp DL360 G5
Simple template to monitor ipmi hp DL360 G5 server by ipmi protocol by iLO interface.
useful with my hp ipmi Drives discovery template
Please first corretly configure ipmi interface on node in zabbix web interface.

##ipmi hp DL360 G6
Simple template to monitor ipmi hp DL360 G6 server by ipmi protocol by iLO interface.
useful with my hp ipmi Drives discovery template
Please first corretly configure ipmi interface on node in zabbix web interface.
This pack contains of two different templates: ipmi hp DL360 G6.xml - contains all sensors ipmi hp DL360 G6 noHDD.xml - contains all sensors except hard drives I prefer use template with noHDD option and my ipmi HDD discovery template, but you can use any.

##ipmi hp DL360p G8
Simple template to monitor ipmi hp DL360p G8 server by ipmi protocol by iLO interface.
useful with my hp ipmi Drives discovery template
Please first corretly configure ipmi interface on node in zabbix web interface.
This pack contains of two different templates: IPMI HP DL360p Gen8.xml - contains all sensors IPMI HP DL360p Gen8 noHDD.xml - contains all sensors except hard drives I prefer use template with noHDD option and my ipmi HDD discovery template, but you can use any.

##ipmi hp DL360p G9
Simple template to monitor ipmi hp DL360p G9 server by ipmi protocol by iLO interface.
useful with my hp ipmi Drives discovery template
Please first corretly configure ipmi interface on node in zabbix web interface.
This pack contains of two different templates: IPMI HP DL360p Gen9.xml - contains all sensors IPMI HP DL360p Gen9 noHDD.xml - contains all sensors except hard drives I prefer use template with noHDD option and my ipmi HDD discovery template, but you can use any.

##ipmi hp DL380p G9 without Drives
Simple template to monitor ipmi hp DL380p G9 server by ipmi protocol by iLO interface.
useful with my hp ipmi Drives discovery template
Please first corretly configure ipmi interface on node in zabbix web interface.
This pack contains template: IPMI HP DL380p Gen9 without Drives.xml - contains all sensors except hard drives I prefer use template with noHDD option and my ipmi HDD discovery template.

##Nec PNMSj
Monitor critical services for NEC PNMSj system

##SNMP Sun M5000 xscf
Simple template to monitor Sun M5000 server over SNMP by XSCF
This template contains:
Firmware state, Hardware state, Ambient Temperature, Serial Number, System State, System Type
CPU discovery
Fan Discovery
Memory board discovery
Memory Unit discovery

##Sun blade 2000
Template parse prtdiag on Sun blade 2000 server command and get:
ASIC status
CPU status
FAN status
PCI cards status
Temperature status
First install supported agent on Operating system (try older versions)

##Sun enterprise T2000 server
Template parse prtdiag on Sun enterprise T2000 server command and get:
CPU status
HDD status
Fan status
MB sensors status
PSU status
Temperature status 

##Sun M4000 prtdiag
Simple template to monitor Sun M4000 server
To use it install zabbix agent on M4000 server and copy conf file to use userparameter settings.
This template contains:
IO devices OK count
memory ok count

##Sun Ultra 80
Simple template to monitor Sun Ultra 80
To use it install zabbix agent on ultra80 server and copy conf file to use userparameter settings.
This template contains:
Overal hardware status

##Sun v440
Simple template to monitor Sun v440 server
To use it install zabbix agent on v440 server and copy conf file to use userparameter settings.
This template contains:
CPU status
HDD status
Fan status
MB sensors status
PCI status
PSU status
Temperature sensors
Voltage status

##Sun v890
Simple template to monitor Sun v890server
To use it install zabbix agent on v890 server and copy conf file to use userparameter settings.
This template contains:
CPU status
HDD status
Fan status
MB sensors status

##Veritas disks discovery on Solaris Sparc
Template to do Veritas disks discovery on Solaris Sparc

##ProximVision NMS.xml
Monitor critical services for ProximWireless Proximvision NMS

##Junos Space.xml
monitor critical services for Junos Space monitoring system

##cisco UCS snmp.xml
Based on https://share.zabbix.com/cat-server-hardware/cisco/cisco-ucs-standalone-hw-monitoring
Contains:
MB operation state
rack serial number
Discoveries:
Arrays
CPUs
Disks
Fans
Memory
PSU
Raid batterys
Raid controllers