NOTE: My own personal fork. I will be maintaining this version specific to my installation of Observium.
Current: Observium CE 0.16.1.7533
Use is not advised.


1. Install the Weathermap in the Observium / LibreNMS folder

```
    cd /opt/observium/html 
    git clone https://github.com/nicolasvion/weathermap-for-observium.git weathermap
```

2. Set weathermap dir to chown apache:apache & chmod 755

3. Run permFix.sh from inside weathermap

4. Add line to cron.d/observium: */5 * * * * root cd /opt/observium/html/weathermap/ && ./map-poller.php && ./permFix.sh >> /dev/null 2>&1

5. If you are installing this into Observium then you can use the navbar-custom.inc.php by putting it into /opt/observium/html/includes/.
