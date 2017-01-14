# Linux related pages
------

## Add Service to ubuntu
------

1.Make sure you have a script in `/etc/init.d`
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

2.Add service to System Service
 * `sudo update-rc.d 'service' defaults`
 * `sudo update-rc.d 'service' enable`

3.Start or Stop you service
 * `sudo service 'service' start|stop|restart`
 

## Other
------

All service and software install process and configure