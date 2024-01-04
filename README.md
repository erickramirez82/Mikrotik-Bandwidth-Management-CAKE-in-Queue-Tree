# Mikrotik-Bandwidth-Management-CAKE-in-Queue-Tree
Mikrotik Bandwidth Management - CAKE in Queue Tree


```
/queue type
add cake-flowmode=dual-srchost cake-nat=yes kind=cake name=cake-upload-ips1
add cake-flowmode=dual-dsthost cake-nat=yes kind=cake name=cake-download-ips1
/queue tree
add bucket-size=0.01 max-limit=300M name=download packet-mark=no-mark parent=bridge queue=cake-download-ips1
add bucket-size=0.01 max-limit=300M name=upload packet-mark=no-mark parent=ether5-wan queue=cake-upload-ips1
```

Test https://www.waveform.com/tools/bufferbloat
