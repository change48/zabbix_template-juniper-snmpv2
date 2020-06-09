#### zabbix-template-for-juniper-snmpv2
2020-03-20 update
* add TxLaserPower items，if you need monitor Tx please download "template-add_TxLaserPower.xml"
* set TxLaserPower-Trigger threshold  on -10dbm or 0dbm,
* added lsi-interfaces in to filters,you can change in filters seting page.   
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~

Based on Zabbix's official Template Net Juniper SNMPv2, only minor modifications have been made.
* The interfaces in the down and shutdown states have been filtered. 
* The virtual interfaces have also been filtered, (vme|lsi|pfe|pfh|\.0|bme|gr|gre|tap|irb|dsc|ipip|pimd|pime|mtun|em0|em1|em2|esi|jsrv|vtep|me|lt|ip|lc|ut|mt|vt|pe|cbp|ud|fxp|dem|pip|pp|et|ae)


* The trigger  threshold seting  is -19dbm or 0dbm. 
* only RxLaserPower items,if you need TxLaserPower items but don’t know how to do it, please email me.

##### The above settings or filters are free to change according to requirements，and please change!

It has been tested and can be used in juniper mx、ex、qfx series,and junos version from 12 to 17.
* If your junos version is lower than 15, you may not be able to monitor the optical power of the Gigabit interface.Please filter the "ge" interface in {#IFNAME} or upgrade junos.
* Another problem is that I have not been able to make a 40G interface LLD. If you have a 40G interface & junos15 above , please feel free to test and modify it.

I haven't figured out how to chat on github，so my email is whye1700#gmail.com(replace # with @)

Juniper-optical-interface是基于官方Template Net Juniper SNMPv2做了简单修改，中文环境用户可以使用template-for-cn-user.xml
* 过滤了down、关闭状态的端口. 
* 很多无用的虚接口也一起过滤了, 具体如下(vme|lsi|pfe|pfh|\.0|bme|gr|gre|tap|irb|dsc|ipip|pimd|pime|mtun|em0|em1|em2|esi|jsrv|vtep|me|lt|ip|lc|ut|mt|vt|pe|cbp|ud|fxp|dem|pip|pp|et|ae)
* 触发器阈值设置为-19dbm和0dbm，这个-19是日常运维经验，可以根据需要灵活修改
* 已经在juniper mx、ex、qfx系列测试可以使用，junos版本从12到17都有，有些交换比如EX4550版本太低的话没有收发光OID没法监控
* 同上，如果你的junos版本低于15，可能没法监控到千兆ge接口的收光数据，原因也是没有OID，可以升级junos或者在{#IFNAME}过滤接口名称。
* 我所在的生产环境40G光口都运行在较低版本的设备上，所有没有环境去做40G接口的LLD，低于15的junos也没有40G接口收发光OID，如果你有这个环境，请随意测试修改。
* 不怎么关注发光，所有监控项只做了收光，如果你需要监控发光但不知道怎么修改模板也可以联系我给你发一个。

邮件：whye1700#gmail.com (#替换为@)








