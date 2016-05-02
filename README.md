zabbixAgentConfig
=================

Intro
=====

A repo for zabbix agent userparamter files, usually dropped into /etc/zabbix/zabbix_agentd.d on a linux host running the zabbix agent.

__Some of this configs require passwords in other files to work (e.g. mysql.conf)__

* `discovery.conf` - Not mine downloaded from the internet, user to discover disks to monitor on a linux host
* `disk.conf` - Not mine, downloaded from the intertubes, used to pickup detailed disk info
* `dns.conf` - Uses `/usr/bin/dig` to return DNS query time, reponse type (e.g. A or txt etc..), DNS record (e.g. IP or CNAME), txt (for checking SPF records etc...)
* `memstat.conf` - Uses `/proc/meminfo` to pull Mem Cache info like file cache size (active vs inactive) and buffers
* `mysql.conf` - Not mine, needs `my.cnf` with password for Zabbix user to work
* `mythtv.conf` - Checks for B sized recordings (duff ones), and which encoders are active
* `ntp.conf` - Checks if an ntpd server is synced, and what the offset is
* `speedtest.conf` - Needs `speedtest-cli` running from cron which dumps info into syslog - this grabs ping, download and upload speeds
* `statTouch.conf` - Returns type of filesystem so that you can monitor if an NFS share is present,y and if it is writable (touch)
* `tcpstat.conf` - Not mine - used to monitor TCP/UDP stats from `/proc/net/sockstat`
* `tls.conf` - Used to monitor TLS cert age, needs `tlsCertAgeCheck` from this repo


Dependencies
============

* `discovery.pl`
* `my.cnf` with password
* `speedtest-cli` logging to syslog - [https://github.com/sivel/speedtest]
* `tlsCertAgeCheck` from this repo
