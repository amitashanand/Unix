# Unix

### netstat
Useful tool for checking your network configuration and activity.
Print network connections, routing tables, interface statistics, masquerade connections, and multicast memberships


Listing all ports
```bash
netstat -a | more
```
Other network protocol Ports connections
```bash
netstat -at   # TCP
netstat -au   # UDP
netstat -ax   # Sockets
```

Show the PID and name of the program to which each socket belongs.
```bash
netstat -p
```


#### LISTENING Connections
```bash
netstat -l    # all
netstat -lt   # TCP
netstat -lu   # UDP
netstat -lx   # UNIX listening ports
```

### Showing Statistics by Protocol
```bash
netstat -s    # TCP, UDP, ICMP, and IP protocols.
netstat -st   # TCP
netstat -su   # UDP
```
### Continuous Listening
```bash
netstat -anlpc |grep 8080
```
### Important command:
List the network open ports on your Linux server and the process that owns them
```bash
netstat -tulpn
netsta -tunlp | grep 22
lsof -i
# -t : TCP
# -u : UDP
# -n : Show numerical addresses instead of trying to determine symbolic host, port or user names
# -l : Show only listening
# -p : Show the PID and name of the program to which each socket belongs
```
Good link to find more [here](https://explainshell.com/)