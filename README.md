NOTE: My own personal fork. I will be maintaining this version specific to my installation of Observium.
Current: Observium CE 0.16.1.7533
Use is not advised.


1. Install the Weathermap in the Observium / LibreNMS folder

```
    cd /opt/observium/html 
    git clone https://github.com/rk4an/weathermap-for-observium.git weathermap
```

2. Set weathermap dir to chown apache:apache & chmod 755

3. Run permFix.sh from inside weathermap

4. Add line to cron.d/observium: */5 * * * * root cd /opt/observium/html/weathermap/ && ./map-poller.php && ./permFix.sh >> /dev/null 2>&1

5. If you are installing this into Observium then you can use the navbar-custom.inc.php by putting it into /opt/observium/html/includes/.
MAKE SURE TO CHOWN/CHMOD IT!

6. Fix this file: /usr/share/php/Console/Getopt.php and change PEAR::isError to @PEAR::isError

7. Move overlib.js down one directory (mv overlib.js ..) so it's down in /opt/observium/html/
