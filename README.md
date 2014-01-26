Zabbix - Proxmox/OpenVZ
==============

Zabbix Template for monitoring your Proxmox/OpenVZ Server

'''
UserParameter=custom.pve.vzlist,/var/lib/zabbix/scripts/vzdiscover.sh
UserParameter=custom.vz.cpu[*],sudo /usr/sbin/vzlist -a -o laverage -H $1       | awk -F/ '{print $$1}'
UserParameter=custom.vz.cpu5[*],sudo /usr/sbin/vzlist -a -o laverage -H $1      | awk -F/ '{print $$2}'
UserParameter=custom.vz.cpu10[*],sudo /usr/sbin/vzlist -a -o laverage -H $1     | awk -F/ '{print $$3}'

UserParameter=custom.vz.usedmem[*],sudo /usr/sbin/vzlist -a -o physpages -H $1 | awk '{print $$1*4/1024}'
'''