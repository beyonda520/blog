# Linux related pages
------

## Add Service to ubuntu
------

1. Make sure you have a script in `/etc/init.d`
  * You could copy an existing file and then modify it according to your needs.
  * Then content should like the following
      ```
      #!/bin/bash
      
      # Sonar Linux service controller script
      cd "/opt/sonar/sonarqube-5.6.4/bin/linux-x86-64/"
      
      case "$1" in
          start|stop|restart)
              ./sonar.sh $1
              ;;
          *)
              echo "Usage: $0 {start|stop|restart}"
              exit 1
              ;;
      esac
      ```

2. Add service to System Service
 * `sudo update-rc.d 'service' defaults`
 * `sudo update-rc.d 'service' enable`

3. Start or Stop you service
 * `sudo service 'service' start|stop|restart`
 

## Other
------

All service and software install process and configure


## XX-net in ubuntu
------

1. Download from github.
2. Unzip it.
3. Start with `sudo start`
4. Check `CA status`, if it's fail, delete certs in `Chromium` and `Firefox` and re-import it through `certutil`.
5. Full bash script is below:
```
   sudo certutil -d sql:$HOME/.pki/nssdb -A -t TC -n "goagent" -i ./data/gae_proxy/CA.crt
```

## 