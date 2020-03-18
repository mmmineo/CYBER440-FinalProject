# Network Analysis Summary

PCAPs analyzed using tshark and Python

## Devices

IP Address      | MAC Address     | Suspected Role
--------------- | --------------- | --------------
192.168.100.1   | Dell_8f:09:45   | VMWare Console/Hypervisor
192.168.100.4   | Dell_a1:82:00   | *Unknown*
192.168.100.5   | Dell_a1:6a:dd   | Host
192.168.100.10  | VMware_0b:e9:e1 | Domain Controller
192.168.100.11  | VMware_38:68:41 | Host
192.168.100.12  | VMware_7e:ed:26 | Host
192.168.100.13  | VMware_13:86:e5 | Host
192.168.100.14  | VMware_45:d3:0e | Host
192.168.100.17  | VMware_82:e1:2d | Host
192.168.100.18  | VMware_75:b1:e1 | Host
192.168.100.19  | VMware_0d:c1:c5 | Host
192.168.100.20  | VMware_14:71:4f | Host
192.168.100.21  | VMware_95:d5:c7 | Host
192.168.100.180 | VMware_01:bf:ed | Host

### 192.168.100.1

Claimed to be the DC in Network Diagrams (see DiskAnalysis.md), but doesn't communicate on port 389. The only ports exchanged between 192.168.100.1 and any arbitrary host are on either TCP 902 (VMWare Console), TCP 443 (HTTPS), TCP 80 (HTTP), or an ephemeral port. This can't be the DC.

Conversation source .1 port dest any - `Counter({'902': 4849898, '443': 54481, '80': 20182})`

Conversation source .1 port dest .4 - `Counter({'902': 4413597, '443': 35858, '80': 10097})`

Conversation source .1 port dest .5 - `Counter({'902': 436301, '443': 18623, '80': 10085})`

Addresses in `ip.addr==192.168.100.1`:
`Counter({'192.168.100.1': 6035049, '192.168.100.4': 4459552, '192.168.100.5': 471298})`

### 192.168.100.4

This device doesn't source any ports less than 1024. Only talks to 192.168.100.1.

Services running - 902 (VMWare Console), possibly 443/80

Conversation source .1 port dest .4 - `Counter({'902': 4413597, '443': 35858, '80': 10097})`

Addresses in `ip.addr==192.168.100.4`:
`Counter({'192.168.100.1': 5516092, '192.168.100.4': 4459552, '224.0.0.22': 1164, '224.0.0.252': 458, '192.168.100.255': 30})`

### 192.168.100.5

Ports indicate this machine is a host.

Conversation source .5 port dest any - None under 1024

Addresses in `ip.addr==192.168.100.5`:
`Counter({'192.168.100.1': 518957, '192.168.100.5': 471390, '192.168.100.255': 281, '192.168.100.10': 72, '239.255.255.250': 42, '192.168.100.11': 27, '192.168.100.18': 18, '224.0.0.22': 11, '224.0.0.251': 2, '224.0.0.252': 1})`

### 192.168.100.10

Claimed to be the IT machine in Network Diagrams. Operates more like a DC.

Services running - 445 and 139 (SMB), 143 (IMAP), 88 (Kerberos), 389 (LDAP)

Conversation source .10 port dest any - `Counter({'445': 212490, '143': 42307, '88': 31663, '139': 10443, '389': 4458, '135': 2517, '587': 578})`

Conversation source .10 port dest .20 - `Counter({'143': 3133, '445': 249, '88': 200, '389': 105, '587': 69, '135': 34})`

Conversation source .10 port dest .11 - `Counter({'445': 201682, '139': 10366, '143': 2205, '88': 642, '389': 594, '135': 249, '587': 166})`

Conversation source .10 port dest .17 - `Counter({'143': 27572, '445': 521, '88': 119, '389': 99, '587': 96, '135': 37})`

Addresses in `ip.addr==192.168.100.10`:
`Counter({'192.168.100.10': 479674, '192.168.100.11': 217777, '192.168.100.19': 81551, '192.168.100.12': 81173, '192.168.100.14': 43798, '192.168.100.180': 32730, '192.168.100.17': 29085, '192.168.100.21': 13902, '192.168.100.13': 4290, '192.168.100.20': 4013, '192.168.100.18': 2392, '192.168.100.16': 1851, '192.168.100.255': 432, '255.255.255.255': 326, '224.0.0.252': 143, '192.168.100.5': 56, '239.255.255.250': 32})`

### 192.168.100.11

Ports indicate this machine is a host.

Conversation source .11 port dest any - `Counter({'139': 7343, '143': 180, '445': 24, '80': 3})`

Addresses in `ip.addr==192.168.100.11`:
`Counter({'192.168.100.11': 227550, '192.168.100.10': 211704, '192.168.100.21': 6052, '192.168.100.255': 2386, '192.168.100.13': 924, '192.168.100.16': 568, '192.168.100.19': 342, '192.168.100.17': 277, '192.168.100.14': 154, '192.168.100.18': 72, '239.255.255.250': 47, '192.168.100.20': 24, '192.168.100.5': 20, '224.0.0.22': 9, '192.168.100.12': 8, '224.0.0.252': 6})`

### 192.168.100.12

Ports indicate this machine is a host.

Conversation source .12 port dest any - `Counter({'80': 220})`

Addresses in `ip.addr==192.168.100.12`:
`Counter({'192.168.100.12': 81330, '192.168.100.10': 81295, '192.168.100.18': 162, '224.0.0.251': 53, 'ip.dst': 41, '192.168.100.14': 34, '192.168.100.20': 19, '192.168.100.11': 5})`

### 192.168.100.13

Port indicate this machine is a host.

Conversation source .13 port dest any - `Counter({'139': 130})`

Addresses in `ip.addr==192.168.100.13`:
`Counter({'192.168.100.13': 5275, '192.168.100.10': 4801, '192.168.100.11': 1104, '192.168.100.255': 370, '224.0.0.22': 178, '224.0.0.252': 178, '239.255.255.250': 143, '192.168.100.14': 44, 'ip.dst': 41, '255.255.255.255': 13, '192.168.100.18': 9})`

### 192.168.100.14

Ports indicate this machine is a host.

Conversation source .14 port dest any - `Counter({'139': 32})`

Addresses in `ip.addr==192.168.100.14`:
`Counter({'192.168.100.10': 46139, '192.168.100.14': 44214, '192.168.100.255': 1109, '224.0.0.252': 914, '224.0.0.22': 761, '192.168.100.21': 597, '239.255.255.250': 364, '192.168.100.11': 152, '255.255.255.255': 91, '192.168.100.13': 54, 'ip.dst': 41, '192.168.100.12': 31, '192.168.100.18': 19, '192.168.100.5': 2})`

### 192.168.100.17

Ports indicate this machine is a host.

Conversation source .17 port dest any - None under 1024

Addresses in `ip.addr==192.168.100.17`:
`Counter({'192.168.100.17': 29394, '192.168.100.10': 17956, '192.168.100.11': 340, '192.168.100.255': 306, '224.0.0.252': 152, '224.0.0.22': 141, '192.168.100.19': 52, '239.255.255.250': 48, 'ip.dst': 41, '255.255.255.255': 12, '192.168.100.18': 4})`

### 192.168.100.18

Ports indicate this machine is a host.

Conversation source .18 port dest any - None under 1024

Addresses in `ip.addr==192.168.100.18`:
`Counter({'192.168.100.10': 2812, '192.168.100.18': 2692, '192.168.100.255': 294, '224.0.0.252': 177, '224.0.0.22': 161, '192.168.100.12': 97, '192.168.100.11': 79, '239.255.255.250': 69, 'ip.dst': 41, '192.168.100.14': 21, '255.255.255.255': 13, '192.168.100.5': 12, '192.168.100.13': 7, '192.168.100.21': 6})`

### 192.168.100.19

Ports indicate this machine is a host.

Conversation source .19 port dest any - `Counter({'443': 351})`

Addresses in `ip.addr==192.168.100.19`:
`Counter({'192.168.100.10': 82020, '192.168.100.19': 81909, '192.168.100.11': 351, '224.0.0.251': 124, 'ip.dst': 41, '192.168.100.17': 32, '192.168.100.255': 6})`

### 192.168.100.20

Ports indicate this machine is a host.

Conversation source .20 port dest any - None under 1024

Addresses in `ip.addr==192.168.100.20`:
`Counter({'192.168.100.20': 4056, '192.168.100.10': 3025, '192.168.100.255': 82, 'ip.dst': 41, '192.168.100.11': 23, '224.0.0.252': 22, '192.168.100.12': 21, '224.0.0.22': 20, '239.255.255.250': 6, '192.168.100.18': 4, '255.255.255.255': 3})`

### 192.168.100.21

Ports indicate this machine is a host.

Conversation source .21 port dest any - `Counter({'139': 22})`

Addresses in `ip.addr==192.168.100.21`:
`Counter({'192.168.100.21': 20557, '192.168.100.10': 13540, '192.168.100.11': 6869, '192.168.100.255': 2476, '224.0.0.22': 1565, '224.0.0.252': 1137, '239.255.255.250': 358, '192.168.100.14': 178, '255.255.255.255': 92, 'ip.dst': 41, '192.168.100.18': 8})`

### 192.168.100.180

Ports indicate this machine is a host.

Conversation source .180 port dest any - None under 1024

Addresses in `ip.addr==192.168.100.180`:
`Counter({'192.168.100.180': 32730, '192.168.100.10': 14442, 'ip.dst': 41, '224.0.0.251': 35, '192.168.100.255': 4, '224.0.0.22': 4, '255.255.255.255': 2})`
