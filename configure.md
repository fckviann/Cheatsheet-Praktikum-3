
1. RhodesIsland
```
auto eth0
iface eth0 inet dhcp
	up echo nameserver 8.8.8.8 > /etc/resolv.conf
	up chmod +x /root/init.sh
	up /root/init.sh

auto eth1
iface eth1 inet static
    address 10.207.1.1
    netmask 255.255.255.0

auto eth2
iface eth2 inet static
    address 10.207.2.1
    netmask 255.255.255.0
```

2. Lungmen
```
auto eth0
iface eth0 inet static
    address 10.207.1.2
    netmask 255.255.255.0
    gateway 10.207.1.1
	up echo nameserver 8.8.8.8 > /etc/resolv.conf
	up chmod +x /root/init.sh
	up /root/init.sh

auto eth1
iface eth1 inet static
    address 10.207.3.1
    netmask 255.255.255.0
    gateway 10.207.1.1
```

3. Ursus
```
auto eth0
iface eth0 inet static
    address 10.207.2.2
    netmask 255.255.255.0
    gateway 10.207.2.1
	up echo nameserver 8.8.8.8 > /etc/resolv.conf
	up chmod +x /root/init.sh
	up /root/init.sh

auto eth1
iface eth1 inet static
    address 10.207.4.1
    netmask 255.255.255.0
    gateway 10.207.1.1
```

4. Victoria (kea-dhcp4)
```
auto eth0
iface eth0 inet static
    address 10.207.3.2
    netmask 255.255.255.0
    gateway 10.207.3.1
	up echo nameserver 8.8.8.8 > /etc/resolv.conf
	up chmod +x /root/init.sh
	up /root/init.sh
```

5. Columbia
```
auto eth0
iface eth0 inet dhcp
```

6. Yan (kea-dhcp4 with IP Booking)
```
auto eth0
iface eth0 inet static
    address 10.207.4.2
    netmask 255.255.255.0
    gateway 10.207.4.1
	up echo nameserver 8.8.8.8 > /etc/resolv.conf
	up chmod +x /root/init.sh
	up /root/init.sh
```

7. Laterano (Web HTML, iperf server, testing file)    
```
auto eth0
iface eth0 inet dhcp
	up echo nameserver 8.8.8.8 > /etc/resolv.conf
	up chmod +x /root/init.sh
	up /root/init.sh
```