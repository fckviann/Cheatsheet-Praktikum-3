
1. delete netem loss
```
tc qdisc del dev eth1 root
```

2. add netem loss
```
tc qdisc add dev eth1 root netem loss 1%
```

3. show netem loss
```
tc qdisc show dev eth1
```

4. download file
```
curl -o /dev/null -s -w "size=%{size_download}B speed=%{speed_download}B/s total=%{time_total}s\n" http://10.207.4.15:9999/tes5M.bin
```

5. limit download rate
```
tc qdisc add dev eth1 root handle 1: tbf rate 2mbit burst 32kbit latency 100ms
```

6. loss-latency (delay) chain
```
tc qdisc add dev eth1 parent 1:1 handle 10: netem delay 100ms loss 1%
```

7. CUBIC Algorithm
```
ip tcp_metrics flush
sysctl -w net.ipv4.tcp_no_metrics_save=1
sysctl -w net.ipv4.tcp_congestion_control=cubic
sysctl net.ipv4.tcp_congestion_control
```

8. RENO Algorithm
```
sysctl -w net.ipv4.tcp_congestion_control=reno
ip tcp_metrics flush
ysctl net.ipv4.tcp_congestion_control
```

9. iperf server
```
iperf3 -s
```

10. iperf client TCP
```
iperf3 -c 10.207.4.15 -t 10
```

11. iperf client UDP
```
iperf3 -c 10.207.4.15 -u -b 5M -t 10
```

12. curl throughput (download speed) and total download time
```
curl -o /dev/null -s -w "Throughput: %{speed_download} B/s\nWaktu Total: %{time_total} detik\n" http://10.207.4.15:9999/5M.bin
```


