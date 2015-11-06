# vxlan_tool
VXLAN Tool 

This was started with a copy of https://github.com/opendaylight/sfc/blob/master/sfc-test/nsh-tools/vxlan_tool.py written by Yi Yang and Reinaldo Penno

Initially, this code was modified to
* run with Python 2.7
* swap the IP SA and DA when forwarding.
* Work for either port 4790 or 6633
* Added verbose option to turn off prints when in forward mode

Options:
* -i: Interface to receive, and optionally send packets on
* -d: Mode: 'dump' or 'forward'.  Default is dump.
* -v: Verbose: 'on' or 'off'.  Default is 'on', and 'off' only works in 'forward' mode.

Example Use:

```
sudo ./vxlan_tool.py -i 'eth1' -d 'forward' -v 'off'
```

vxlan_tool uses a raw socket to recieve and send packets.  Even though vxlan_tool is handling the packets, the host will sent an ICMP unreachable message because it doesn't know that anything is listening on the UDP ports.

