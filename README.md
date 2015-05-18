zabbix-xenserver-templates
==================================

Zabbix templates for Citrix XenServer and zabbix-sender for monitoring.

This templates and programs inspire by following programs of Emir Imamagic.

 Citrix XenAPI/RRDs monitoring
 https://www.zabbix.com/forum/showthread.php?t=25121

Version
----------------
 0.1

Usage
----------------
TBD
- import templates.
- /usr/libexec/zabbix-agentd
- cp zabbix-agentd/*.py /usr/libexec/zabbix-agentd
- cp citrix.conf /etc/zabbix/agent-conf.d
- edit XenServerVM-regist.pl
- exec XenServerVM-regist.pl

## TODO
- Rewrite by perl or python..
- code cleanup.
- Write "Usage"

## Install zabbix on XenServer
```
yum --enablerepo=base install openssl-devel curl-devel
rpm -ivh http://repo.zabbix.com/zabbix/2.2/rhel/5/i386/zabbix-2.2.6-1.el5.i386.rpm
rpm -ivh http://repo.zabbix.com/zabbix/2.2/rhel/5/i386/zabbix-agent-2.2.6-1.el5.i386.rpm
rpm -ivh http://repo.zabbix.com/zabbix/2.2/rhel/5/i386/zabbix-sender-2.2.6-1.el5.i386.rpm
sed -i  's/Server=.*/Server=10.0.11.6/g' /etc/zabbix/zabbix_agentd.conf 
/etc/init.d/zabbix-agent restart
chkconfig zabbix-agent on
```
