# EX 2
_A local lan with 2 pcs, a default gateway that also operates as a DHCP
server.
The assignment is: to manually configure r1 to act as DHCP server and
the 2 pcs to request an IP address from it._

- _r1 is set up with the IP address 192.168.100.30/28. It should use
  the network 192.168.100.16/28 as the address pool_

- _the DNS server can be the server used by the host machine (this has
  to be set in all the pc of the lab)_

- _the default gateway is r1_

- _pc1 should be configured using the interfaces file_

- _pc2 should be configured using the dhclient command_

![image](https://user-images.githubusercontent.com/74598295/223479333-bb333bfd-9025-4014-a056-9a54f60042d3.png)

## R1:
Before starting the lab, change the "lab.conf" file's line 
```
r1[0] = 'lanA'
```
INTO 
```
r1[0] = "lanA"
```

YOU HAVE TO CHANGE THE FILE "/etc/udhcpd.conf" in order to make it work.
What to change:

	> start		192.168.100.25

	> end		192.168.100.29

	> max_leases 8

	> opt dns 1.1.1.1

	> option subnet 255.255.255.240

	> option router 192.168.100.30`
	
	
After that we are able to run "udhcpd"

## PC1: 
#### interfaces setting

- just create a file in "/pc1/etc/network/interface" from GUI (do not lstart yet)
- the file content is:
	```			
	auto eth0
	allow-hotplug eth0
	iface eth0 inet dhcp 
	```
	
				
- run "ifup eth0" and pc1 should get its IP


## PC2: 
#### dhclient

- make sure the dns is the same as the router (through "etc/resolv.conf")
- run "dhclient"
- this pc should have an ip addr now












