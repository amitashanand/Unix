# Unix

### systemctl
 `systemctl` is the central management tool for controlling the init system `(systemd)`.
 `systemd` is the default init system for many Linux distributions
 The fundamental purpose of an init system is to initialize the components that must be started after the Linux kernel is booted.
 The fundamental purpose of an init system is to initialize the components that must be started after the Linux kernel is booted
 In systemd, the target of most actions are “units”, which are resources that systemd knows how to manage.
 Units are categorized by the type of resource they represent and they are defined with files known as unit files.
 #### Starting and Stopping Services

 ```bash
 sudo systemctl start application.service
 ```
 ```bash
 sudo systemctl stop application.service
 ```

 #### Restarting and Reloading
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

 #### Enabling and Disabling Services
 To tell systemd to start services automatically at boot, you must enable them.
 ```bash
 sudo systemctl enable application.service
 ```
 This will create a symbolic link from the system’s copy of the service file (usually in /lib/systemd/system or /etc/systemd/system) into the location on disk where systemd looks for autostart files (usually /etc/systemd/system/some_target.target.wants.
 To disable the service from starting automatically:
```bash
sudo systemctl disable application.service
```
#### Checking the Status of Services
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

### System State Overview
#### Listing Current Units
To see a list of all of the active units that systemd knows about
```bash
systemctl list-units
```
This is also the default behavior of
```bash
systemctl 
```
To see all of the units that systemd has loaded (or attempted to load), regardless of whether they are currently active

```bash
systemctl list-units --all 
```
With filters:
```bash
systemctl list-units --all --state=inactive
systemctl list-units --type=service
```
#### Listing All Unit Files
```bash
systemctl list-unit-files
```
### Unit Management
To display unot file
```bash
systemctl cat atd.service
```
To display dependencies
```bash
systemctl list-dependencies sshd.service
```
Editing unit files
```bash
sudo systemctl edit nginx.service
sudo systemctl edit --full nginx.service
```
[Back to Index](README.md)