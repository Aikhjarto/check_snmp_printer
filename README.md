# check_snmp_printer

Nagios/Icinga plugins that read the status of a laser printer via SNMP
(`snmpwalk` from net-snmp), using the standard Printer MIB.

| Plugin | Checks |
|---|---|
| `check_snmp_printer_supply` | Fill level of a supply, e.g. toner or the wear level of the image drum |
| `check_snmp_printer_tray` | Paper level of a tray |

```sh
check_snmp_printer_supply -H printer.example.com -s 1 -w 3 -c 0
check_snmp_printer_tray   -H printer.example.com -t 1 -w 5 -c 0
```

`-H` is required. `-w` and `-c` are levels in percent of the maximum, `-s`
selects the supply and `-t` the tray index, `-d` sets the SNMP community
(default `public`) and `-P` the SNMP version (default 1). `-h` shows the help.
