dkLab vzfailcnt: send OpenVZ failcnt changes over e-mail
(C) Dmitry Koterov, http://en.dklab.ru/lib/vzfailcnt/
License: GPL

This simple script is aimed to watch for a failcnt growth in
/proc/user_beancounters under OpenVZ. In addition, it also watches
for remaining diskspace and diskinodes counters and alerts you when
they exceed a particular threshold (default to 80%).

Vzfailcnt sends you a nice-looking e-mail when above values are
increased. When you call the script periodically (e.g. in 5-minute
cron) and it sees that a failcnt or a remaining diskspace/diskinodes
value is changed, it mails you about that.

The main advantage of the script is that it has zero configuration.
It is also written in pure Perl with no deps on non-standard modules,
so it may be copied to any linux machine with OpenVZ.


INSTALLATION
------------

cd /usr/sbin
wget http://github.com/DmitryKoterov/vzfailcnt/raw/master/vzfailcnt
chmod +x vzfailcnt


SYNOPSIS
--------

1. Send me an e-mail if a failcnt is changed since the last run:
   # /usr/sbin/vzfailcnt your@email.com

2. You may also define your e-mail and other options in /etc/vzfailcnt.conf
   and call vzfailcnt with no arguments:
   # /usr/sbin/vzfailcnt

3. Add script to your crontab using:
   # echo '*/1 * * * * root /usr/sbin/vzfailcnt' > /etc/cron.d/vzfailcnt.cron
