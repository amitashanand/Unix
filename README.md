# Unix

## systemctl
 `systemctl` is the central management tool for controlling the init system `(systemd)`.
 `systemd` is the default init system for many Linux distributions
 The fundamental purpose of an init system is to initialize the components that must be started after the Linux kernel is booted.
 The fundamental purpose of an init system is to initialize the components that must be started after the Linux kernel is booted
 In systemd, the target of most actions are “units”, which are resources that systemd knows how to manage.
 Units are categorized by the type of resource they represent and they are defined with files known as unit files.
 ### Starting and Stopping Services

 ```bash
 sudo systemctl start application.service
 ```
 ```bash
 sudo systemctl stop application.service
 ```

 ### Restarting and Reloading
 ```bash
 sudo systemctl restart application.service
 ```
 if app is able to able to reload its configuration files (without restarting)  
 ```bash
 sudo systemctl reload application.service
 ```
 if unsure reload or restart.This will reload the configuration in-place if available. Otherwise, it will restart the service so the new configuration is picked up
  ```bash
 sudo systemctl reload-or-restart application.service
 ```

 ### Enabling and Disabling Services
 To tell systemd to start services automatically at boot, you must enable them.
 ```bash
 sudo systemctl enable application.service
 ```
 This will create a symbolic link from the system’s copy of the service file (usually in /lib/systemd/system or /etc/systemd/system) into the location on disk where systemd looks for autostart files (usually /etc/systemd/system/some_target.target.wants.
 To disable the service from starting automatically:
```bash
sudo systemctl disable application.service
```
### Checking the Status of Services
```bash
systemctl status application.service
```

```bash
systemctl is-active application.service
```
```bash
systemctl is-enabled application.service
```
```bash
systemctl is-failed application.service
```

