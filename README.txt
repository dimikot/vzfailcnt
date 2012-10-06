dkLab vzfailcnt: send OpenVZ failcnt changes over e-mail
(C) Dmitry Koterov, http://en.dklab.ru/lib/vzfailcnt/
License: GPL

This simple script is aimed to watch for a failcnt growth in
/proc/user_beancounters under OpenVZ. It sends you a nice-looking
e-mail when these values are increased. When you call the script
periodically (e.g. in 5-minute cron) and it sees that a failcnt
value is changed, it mails you about that.

The main advantage of the script that it has a zero configuration.
It is also written in pure Perl with no deps on non-standard modules,
so it may be copied to any linux machine with OpenVZ.


SYNOPSIS
--------

1. Send me an e-mail if a failcnt is changed since the last run:
   /usr/sbin/vzfailcnt your@email.com

2. You may also define your e-mail in /etc/vzfailcnt.conf:
   /usr/sbin/vzfailcnt conf

3. Add script to your crontab using:
   echo '*/1 * * * * root /usr/sbin/vzfailcnt conf' > /etc/cron.d/vzfailcnt.cron
