#### cblpic201

- 02
cpu stress test
```
apt-get install stress
```
run 2 cpu
```
stress -c 2
```
run 6 memory
```
stress -m 6
```

- 03
uptime - show system running time
```
uptime
```
the last 3 params: last1min, 5min, 15min


cpuload:
1cpu 0.5 -> half used 1.5->150% used  
4cup 0.5 ->12.5% 5.0 ->125% used  

io wait:  
percentage of CPU actions waiting for disk access; process is io blocked, and in uninterruptable sleep  

stress test for io:  
watch 'wa' column of ```top``` command
then 
```
stress --hdd 1
```

install iotop tool:
```
sudo apt-get install iotop
sudo iotop
```

Get io instance snapshot:
```
iostat  (first, apt-get install sysstat)
```
sar command
```
sar 1 4 (1sec interval 4times) see %iowait
```

lsof -> list all open files
```
lsof | grep stress
```

- 04
monitering network io
netstat
```
netstat -ie  //interfaces
netstat -s //stats
netstat -tuna //useful info
```

other tools
```
sudo apt-get install iftop nload
```
iftop ->realtime monitering
nload ->interactive network monitering

- 5
bandwidth measuring iperf and speedtest
```
iperf -s //test server speed
iperf -c 192.168.1.1 //test client speed
```

- 6
moniter data trend
```
sudo apt-get install collectd
```
edit 
```
vim /etc/collectd/collectd.conf
```
uncomment network
and enable cgi
```
sudo a2emod cgi
sudo serviceapache2 restart
```

check
```
cd /usr/lib/cgi-bin
```
```
sudo apt-get install liberrds-perl libjson-perl libhtml-parser-perl
```
not finished.  
- 07
kernel components
- 08 manipulate kernel modules
```
uname -r
```

list all modules in system
```
cd /lib/modules
ls
```
go to folder of kernel folder:
```
ls kernel/
```

list system prop
```
lsmod
```

remove a kernel module
```
rmmod floppy
```
inspect a module to identify whether it exits
```
insmod floppy
```

find the folder of folder floppy
```
find . | grep floppy
```

Advanced commands
```
modprobe -r floppy
modprobe floppy
depmod -a
modinfo lp
```




