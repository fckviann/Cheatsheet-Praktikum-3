
1. Victoria (Client Firefox)

```
cat << 'EOF' etc/kea/kea-dhcp4ile.conf
{
  "Dhcp4": {
    "interfaces-config": { "interfaces": ["eth0"] },
    "lease-database": { "type": "memfile", "persist": true, "name": "/var/lib/kea/kea-leases4.csv" },
    "valid-lifetime": 3600,
    "subnet4": [
      {
        "id": 1,
        "subnet": "10.207.3.0/24",
        "pools": [ { "pool": "pool range start - pool range end" } ],
        "option-data": [
          { "name": "routers", "data": "IP gateway Victoria" },
          { "name": "domain-name-servers", "data": "8.8.8.8" }
        ]
      }
    ]
  }
}
EOF
```

2. Yan (BOOK IP, for source html)

```
cat << 'EOF' etc/kea/kea-dhcp4ile.conf
{
  "Dhcp4": {
    "interfaces-config": { "interfaces": ["eth0"] },
    "lease-database": { "type": "memfile", "persist": true, "name": "/var/lib/kea/kea-leases4.csv" },
    "valid-lifetime": 3600,
    "subnet4": [
      {
        "id": 1,
        "subnet": "10.207.4.0/24",
        "pools": [ { "pool": "pool range start - pool range end" } ],
        "option-data": [
          { "name": "routers", "data": "IP gateway Yan" },
          { "name": "domain-name-servers", "data": "8.8.8.8" }
        ],
        "reservations": [
          { "hw-address": "<MAC eth0 Laterano (12 digit hexadecimal)>", "ip-address": "10.207.4.15" }
        ]
      }
    ]
  }
}
EOF
```