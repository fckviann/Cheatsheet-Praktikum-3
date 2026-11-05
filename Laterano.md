
1. Laterano /root/myscripts/start_http.sh
```
#!/bin/sh
 
mkdir -p myweb
cd myweb
 
python3 -m http.server 9999 -d /root/myscripts/myweb
```
```
chmod +x /root/start_http.sh
./start_http.sh

2. Laterano /root/myscripts/myweb

```
dd if=/dev/random of=tes1000.bin   bs=1    count=1000
dd if=/dev/random of=tes10000.bin  bs=10   count=1000
dd if=/dev/random of=tes50000.bin  bs=50   count=1000
dd if=/dev/random of=tes5M.bin     bs=5000 count=1000
```