# Unix

### journnalctl
 In genearal logs are dispersed throughout the system and handled by differnet daemons and process.
 `systemd` consolidates all these logs and provides centralized management solutioin.
 The system that collects and manages these logs is known as the journal and is implemented with the journald daemon.

 journalctl can be used to access and manipulate the data held within the journal.
 
 #### Setting the System Time
 See what timezones are available
 ```bash
 timedatectl list-timezones
 ```
 Set timezone
 ```bash
 sudo timedatectl set-timezone zone
 ```
 Display timezone and other related information
 ```bash
 timedatectl status
 ```
 #### Basic Log Viewing
see the logs that the journald daemon has collected, use the journalctl.
every journal entry that is in the system will be displayed with oldest at the top.
```bash
journalctl
```
Show you all of the journal entries that have been collected since the most recent reboot.
```bash
journalctl -b
```
To see logs after a given date time:
```bash
journalctl --since "2015-01-10 17:15:00"
journalctl --since "2015-01-10" --until "2015-01-11 03:00"
journalctl --since yesterday
journalctl --since 09:00 --until "1 hour ago"
```

#### Filtering
```bash
journalctl -u nginx.service
journalctl -u nginx.service --since today
```
By Process, User, or Group ID
```bash
journalctl _PID=8088
```
By Priority
```bash
journalctl -p err -b   # err and above will be displayed
```
`0: emerg, 1: alert,2: crit , 3: err, 4: warning, 5: notice, 6: info, 7: debug`

#### Modify Display
truncated output from right of screen
```bash
journalctl --no-full
```
output to other source, use no page fpr entire log
```bash
journalctl --no-pager
```
Follow or Tail
```bash
journalctl -f
journalctl -u mysql.service -f
```
Output format
```bash
journalctl -b -u nginx -o json
journalctl -b -u nginx -o json-pretty
```
Displaying Recent Logs
```bash
journalctl -n # recent 10 entries
journalctl -n 20 #soecify entries
```
#### Deleting Old Logs

```bash
sudo journalctl --vacuum-size=1G
sudo journalctl --vacuum-time=1years
``` 
[Back to Index](README.md)

