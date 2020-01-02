### zabbix-template-for-juniper-snmpv2
Based on Zabbix's official Template Net Juniper SNMPv2, only minor modifications have been made.
* The interfaces in the down and shutdown states have been filtered. 
* The virtual interfaces have also been filtered, (vme|lsi|pfe|pfh|\.0|bme|gr|gre|tap|irb|dsc|ipip|pimd|pime|mtun|em0|em1|em2|esi|jsrv|vtep|me|lt|ip|lc|ut|mt|vt|pe|cbp|ud|fxp|dem|pip|pp|et|ae)
* The trigger  threshold is set to -19dbm.
#### The above settings or filters are free to change according to requirements，and please change!

It has been tested and can be used in juniper mx、ex、qfx series,and junos version from 12 to 17.
* If your junos version is lower than 15, you may not be able to monitor the optical power of the Gigabit interface.Please filter the "ge" interface in #ifname or upgrade junos.
* Another problem is that I have not been able to make a 40G interface LLD. If you have a 40G interface and a version of junos15 or more, please feel free to test and modify it.

