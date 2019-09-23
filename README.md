## About

**check_snmp_memusage_percent** - Icinga Plugin Check Command to calculate the percentage of memory used (from SNMP data)

PreReq: **snpmget** tool


## Usage

Options:

```
$ /usr/lib/nagios/plugins/snmp_memusage_percent.sh [OPTIONS]

Option  Long option       Meaning
------  ---------------   -------
-H      --hostname        Host name, IP Address
-P      --protocol        SNMP protocol version. Possible values: 1|2c|3
-C      --community       SNMPv1/2c community string for SNMP communication (for example,public)
-L      --seclevel        SNMPv3 securityLevel. Possible values: noAuthNoPriv|authNoPriv|authPriv
-a      --authproto       SNMPv3 auth proto. Possible values: MD5|SHA
-x      --privproto       SNMPv3 priv proto. Possible values: DES|AES
-U      --secname         SNMPv3 username
-A      --authpassword    SNMPv3 authentication password
-X      --privpasswd      SNMPv3 privacy password
-t      --total-mem-oid   Total memory OID
-f      --free-mem-oid    Free memory OID
-w      --warning         Warning threshold for memory usage percents
-c      --critical        Critical threshold for memory usage percents
-q      --help            Show this message
-v      --version         Print version information and exit
```

Example for **Digi AnywhereUSB** device:

```
$ ./snmp_memusage_percent.sh -H netdev01.holding.com -P 1 -C public \
-t 1.3.6.1.4.1.332.11.6.1.8.0 \
-f 1.3.6.1.4.1.332.11.6.1.9.0 \
-w 85 -c 95
```
Icinga Director integration manual (in Russian):

[Icinga плагин snmp_memusage_percent для мониторинга процента утилизации памяти по данным, полученным по SNMP](https://blog.it-kb.ru/2017/08/24/icinga-plug-in-snmp_memusage_percent-to-monitor-the-percentage-of-memory-utilization-based-on-data-calculated-from-two-snmp-oids/)
