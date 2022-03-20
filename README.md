# datapower-network-diagnose

Following on DataPower 7.5.2.2 -VMware (MacAir)

idg(config)# show clock

    Local time: Mon Jan  1 02:01:26 2018
     Time zone: UTC
Time zone spec: UTC
Uptime: reload: 0 days 01:42:53
Uptime: reboot: 0 days 01:44:08


idg(config)# exit
idg#
idg#
idg#
idg# show clock

    Local time: Mon Jan  1 02:01:46 2018
     Time zone: UTC
Time zone spec: UTC
Uptime: reload: 0 days 01:43:14
Uptime: reboot: 0 days 01:44:28


idg#
idg# show ntp-service

ntp-service [down] (modified)
-----------
 admin-state disabled
 remote-server 192.168.1.123
 remote-server 192.168.1.124
 refresh-interval 900 Seconds


idg# ntp-service
Unknown command or macro (ntp-service)
idg# co
Global configuration mode
idg(config)#
idg(config)#
idg(config)#
idg(config)# ntp-service
Modify NTP Service configuration

idg(config ntp-service)# cancel
idg(config)#
idg(config)#
idg(config)#
idg(config)#
idg(config)#
idg(config)# show ntp-service

ntp-service [down] (modified)
-----------
 admin-state disabled
 remote-server 192.168.1.123
 remote-server 192.168.1.124
 refresh-interval 900 Seconds


idg(config)# ntp-service
Modify NTP Service configuration

idg(config ntp-service)# no remote-server 192.168.1.123
idg(config ntp-service)# no remote-server 192.168.1.124
idg(config ntp-service)# remote-server time1.google.com
idg(config ntp-service)# show
 admin-state disabled
 remote-server time1.google.com
 refresh-interval 900 Seconds
idg(config ntp-service)# exit
idg(config)#
idg(config)# show ntp-service

ntp-service [down] (modified)
-----------
 admin-state disabled
 remote-server time1.google.com
 refresh-interval 900 Seconds


idg(config)# ntp-service
Modify NTP Service configuration

idg(config ntp-service)# admin-state enabled
idg(config ntp-service)# exit
idg(config)#
idg(config)# show ntp-service

ntp-service [up] (modified)
-----------
 admin-state enabled
 remote-server time1.google.com
 refresh-interval 900 Seconds


idg(config)# show clock

    Local time: Sun Mar 20 09:33:10 2022
     Time zone: UTC
Time zone spec: UTC
Uptime: reload: 0 days 01:47:02
Uptime: reboot: 0 days 01:48:16


idg(config)# show clock

    Local time: Sun Mar 20 09:34:50 2022
     Time zone: UTC
Time zone spec: UTC
Uptime: reload: 0 days 01:48:42
Uptime: reboot: 0 days 01:49:57


idg(config)# timezone
Modify Time Settings configuration

idg(config timezone)# cancel
idg(config)#
idg(config)#
idg(config)# show timezone

timezone [up]
--------
 admin-state enabled
 name UTC
 custom STD
 direction West
 offset-hours 0 Hours
 offset-minutes 0 Minutes
 daylight-offset 1 Hours
 daylight-name DST
 daylight-start-month March
 daylight-start-week 2 Instance
 daylight-start-day Sunday
 daylight-start-hours 2 Hours
 daylight-start-minutes 0 Minutes
 daylight-stop-month November
 daylight-stop-week 1 Instance
 daylight-stop-day Sunday
 daylight-stop-hours 2 Hours
 daylight-stop-minutes 0 Minutes


idg(config)# show timezone

timezone [up] (modified)
--------
 admin-state enabled
 name GMT0BST
 custom STD
 direction West
 offset-hours 0 Hours
 offset-minutes 0 Minutes
 daylight-offset 1 Hours
 daylight-name DST
 daylight-start-month March
 daylight-start-week 2 Instance
 daylight-start-day Sunday
 daylight-start-hours 2 Hours
 daylight-start-minutes 0 Minutes
 daylight-stop-month November
 daylight-stop-week 1 Instance
 daylight-stop-day Sunday
 daylight-stop-hours 2 Hours
 daylight-stop-minutes 0 Minutes

idg(config)# show clock

    Local time: Sun Mar 20 09:39:59 2022
     Time zone: GMT
Time zone spec: GMT0BST,M3.5.0/1:00,M10.5.0/2:00
Uptime: reload: 0 days 01:53:52
Uptime: reboot: 0 days 01:55:06

idg(config)# show clock

    Local time: Sun Mar 20 10:40:26 2022
     Time zone: CET
Time zone spec: CET-1CEST,M3.5.0/2:00,M10.5.0/3:00
Uptime: reload: 0 days 01:54:19
Uptime: reboot: 0 days 01:55:33

idg(config)# show timezone

timezone [up] (modified)
--------
 admin-state enabled
 name CET-1CEST
 custom STD
 direction West
 offset-hours 0 Hours
 offset-minutes 0 Minutes
 daylight-offset 1 Hours
 daylight-name DST
 daylight-start-month March
 daylight-start-week 2 Instance
 daylight-start-day Sunday
 daylight-start-hours 2 Hours
 daylight-start-minutes 0 Minutes
 daylight-stop-month November
 daylight-stop-week 1 Instance
 daylight-stop-day Sunday
 daylight-stop-hours 2 Hours
 daylight-stop-minutes 0 Minutes

idg(config)# show clock

    Local time: Sun Mar 20 10:41:49 2022
     Time zone: CET
Time zone spec: CET-1CEST,M3.5.0/2:00,M10.5.0/3:00
Uptime: reload: 0 days 01:55:41
Uptime: reboot: 0 days 01:56:56

=== Change timezone

idg(config)# show clock

    Local time: Sun Mar 20 10:45:18 2022
     Time zone: CET
Time zone spec: CET-1CEST,M3.5.0/2:00,M10.5.0/3:00
Uptime: reload: 0 days 01:59:11
Uptime: reboot: 0 days 02:00:25


idg(config)#
idg(config)# timezone
Modify Time Settings configuration

idg(config timezone)# name GMT0BST
idg(config timezone)# exit
idg(config)#
idg(config)# show clock

    Local time: Sun Mar 20 09:45:48 2022
     Time zone: GMT
Time zone spec: GMT0BST,M3.5.0/1:00,M10.5.0/2:00
Uptime: reload: 0 days 01:59:40
Uptime: reboot: 0 days 02:00:54


