
1. RhodesIsland
```
#!/bin/sh

ip route add 10.207.3.0/24 via 10.207.1.2 dev eth1
ip route add 10.207.4.0/24 via 10.207.2.2 dev eth2
iptables -t nat -A POSTROUTING -j MASQUERADE -s 10.207.0.0/16 -o eth0
```

2. Lungmen
```
#!/bin/sh

ip route add 10.207.2.0/24 via 10.207.1.1 dev eth0
ip route add 10.207.4.0/24 via 10.207.1.1 dev eth0
```

3. Ursus
```
#!/bin/sh

ip route add 10.207.1.0/24 via 10.207.2.1 dev eth0
ip route add 10.207.3.0/24 via 10.207.2.1 dev eth0
```

4. Victoria (kea-dhcp4)
```
#!/bin/sh

apk add kea-dhcp4
mkdir -p /var/lib /run/kea
kea-dhcp4 -d -c /etc/kea/kea-dhcp4.conf
```

5. Yan (kea-dhcp4 with IP Booking)
```
!/bin/sh

apk add kea-dhcp4
mkdir -p /var/lib /run/kea
kea-dhcp4 -d -c /etc/kea/kea-dhcp4.conf
```

6. Laterano (Web HTML, testing file, iperf server)

```
#!/bin/sh
apk add python3
```

7. Columbia (Client Firefox, Client Download, iperf client)