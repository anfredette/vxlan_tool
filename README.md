# vxlan_tool
VXLAN Tool 

Started with a copy of https://github.com/opendaylight/sfc/blob/master/sfc-test/nsh-tools/vxlan_tool.py

Initially, this code was modified to
* run with Python 2.7 and to swap the 
* swap the IP SA and DA when forwarding.
* Work for either port 4790 or 6633

Example Use:

```
sudo ./vxlan_tool.py -i 'eth1' -d 'forward'
```

vxlan_tool uses a raw socket to recieve and send packets.  Even though vxlan_tool is handling the packets, the host will sent an ICMP unreachable message because it doesn't know that anything is listening on the UDP ports.

