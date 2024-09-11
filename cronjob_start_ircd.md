/home/ircd/cronjob_start_ircd.sh
```
#!/bin/bash
ps -p `cat /home/ircd/ircd/var/run/ircd.pid` > /dev/null 2>&1
if [ $? = 1 ]
  then /home/ircd/ircd/sbin/ircd
fi
```

```
chmod +x /home/ircd/cronjob_start_ircd.sh
```

Add to crontab:
```
*/5 * * * * /home/ircd/cronjob_start_ircd.sh > /dev/null 2>&
```
