# Simple Network using Cisco Packet Tracer

In this project I have decided to create a network using Cisco Packet Tracer. This report will
have every detail of the process, from the infrastructure to the configuration code of the router.
We begin with choosing the right components of the network.
The network we want to create will have two cable networks and a wireless one. We have to
follow these footsteps:
- We choose the components provided from the Packet tracer: one router, two switches
and one access point. Connected in the network will be 4 host machines (PCs), two on
each network, and host machines (LPs) on the access point network. In table 1.0 we will
find a list of the devices used in the network and their description.

| Device      | Model Name  | Qty. |
| :---        |    :----:   | ---: |
| PC          | PC-PT       | 4    |
| LP          | LP-PT       | 2    |
| Switch      | 2960-24TT   | 2    |
| Wireless Device| AccessPoint-PT     | 1    |
| Router        | ISR-331      | 1   |

(Table 1.0: Devices used in the network)

- We have to connect all devices with each other. We have to click on “Connections” and
choose “Copper Straight Through”, because copper is a good conductor of electricity to
send and receive packets.
To connect the laptops with the Access Point, first we need to put the wireless module on those
laptops as an external component. We do this by:
- Turn off the Laptop on the “Physical” tab.
- Remove the Ethernet Module.
- Replace with Wireless Module.
- Turn on.

After this process, the laptop should be automatically connected.
Next step is to connect the switches with the router. This will be done using the GigabitEthernet
port cable. The router we have chosen for the network only has two GigabitEthernet ports, so
we need to add another module using the “Physical” configuration, similar to adding the wireless
hardware to the laptop.

Now we have to configure all machine host devices, in our case the Personal Computers (PC).
We have to give them e Network IP, Subnet Mask and Default Gateway, which will be also
saved in the Router Interface.
To understand the Ip Configuration better, table 1.1 will help with that.

| Device  | IPv4 Address  | Subnet mask | Default Gateway |
| :---    |    :----:     | :---:   | ---: |
| PC 0         | 192.168.10.2       | 255.255.255.0   | 192.168.10.254 |
| PC 1        | 192.168.10.3       | 255.255.255.0    | 192.168.10.254 |
| PC 2      | 192.168.20.2  | 255.255.255.0  | 192.168.20.254 |
| PC 3| 192.168.20.3     | 255.255.255.0  | 192.168.20.254 |
| LP 0 | 192.168.30.2      | 255.255.255.0  | 192.168.30.254 |
| LP 1 |192.168.30.3  |255.255.255.0  | 192.168.30.254 |

(Table 1.1: Ip Configuration on all host machines.)

We can configure the IP in the “Desktop” tab, under “IP Configuration”.

At this phase, all PCs in their network can communicate with each other, but not outside of it; for
example, PC0 and PC1 can communicate with each other, but PC1 and PC3 cannot. For them
to be able to communicate, we have to configure the Ethernet ports of the Router. To do this we
have to click on the “CLI” tab.
- enable // to enable connection with the router as an administrator
- show ip interface brief // to see the active ports in our router
- configure terminal // to start configuration through the terminal
- interface [name of interface port] // to start configuring the chosen port
- ip address [ip address subnet mask] // to activate the network of the port
- no shutdown // this command leaves the network open even after receiving and
transmitting packets
- We do this for every interface: g0/0/0; g0/0/1; g0/0/2
- 
