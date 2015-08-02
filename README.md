# pack-varnish

This pack will help you to monitor key metrics of a varnish cache server

This pack use NRPE to monitor Varnish : 

On the varnish server, you need to configure the following in your nrpe config file :

```
command[check_varnishstat]=/usr/bin/sudo /usr/lib/nagios/plugins/check_varnish.py -f $ARG1$ -w $ARG2$ -c $ARG3$
command[check_specific_procs]=/usr/lib/nagios/plugins/check_procs -a "$ARG1$" -m $ARG2$ -c $ARG3$ -u $ARG4$
```

The script "check_varnish.py" is included in this pack in the libexec directory.
