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
