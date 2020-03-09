# Network Analysis Summary

Brant Goings - CYBER 440

### Noteable Devices

- 192.168.100.1 : Dell_8f:09:45
- 192.168.100.4 : Dell_a1:82:00
- 192.168.100.10 : something : Domain Controller
- 192.168.100.20 : something : 

### Popular Protocols

- SMB
- HTTP
- LDAP

### 192.168.100.1

Claimed to be the DC in Network Diagrams (see DiskAnalysis.md), but doesn't communicate on port 389

Exported `ip.addr==192.168.100.1` to .csv and counted port number occurences.

The only ports exchanged between 192.168.100.1 and any arbitrary host are on either TCP 902 (VMWare Console), TCP 443 (HTTPS), TCP 80 (HTTP), or an ephemeral port. This can't be the DC.

Conversation source .1 dest any - `Counter({'902': 4849898, '443': 54481, '80': 20182})`

Conversation source .1 dest .4 - `Counter({'902': 4413597, '443': 35858, '80': 10097})`

Conversation source .1 dest .5 - `Counter({'902': 436301, '443': 18623, '80': 10085})`

Addresses in `ip.addr==192.168.100.1`:
`Counter({'192.168.100.1': 6035049, '192.168.100.4': 4459552, '192.168.100.5': 471298})`


### 192.168.100.10

Claimed to be the IT machine in Network Diagrams

Conversation source .10 dest any port - `Counter({'445': 212490, '143': 42307, '88': 31663, '139': 10443, '389': 4458, '135': 2517, '587': 578})`

Conversation source .10 dest .20 port - `Counter({'143': 3133, '445': 249, '88': 200, '389': 105, '587': 69, '135': 34})`

Conversation source .10 dest .11 port - `Counter({'445': 201682, '139': 10366, '143': 2205, '88': 642, '389': 594, '135': 249, '587': 166})`

Conversation source .10 dest .17 - `Counter({'143': 27572, '445': 521, '88': 119, '389': 99, '587': 96, '135': 37})`

Addresses in `ip.addr==192.168.100.10`:
`Counter({'192.168.100.10': 479674, '192.168.100.11': 217777, '192.168.100.19': 81551, '192.168.100.12': 81173, '192.168.100.14': 43798, '192.168.100.180': 32730, '192.168.100.17': 29085, '192.168.100.21': 13902, '192.168.100.13': 4290, '192.168.100.20': 4013, '192.168.100.18': 2392, '192.168.100.16': 1851, '192.168.100.255': 432, '255.255.255.255': 326, '224.0.0.252': 143, '192.168.100.5': 56, '239.255.255.250': 32})`

### 192.168.100.20

All counters below do not include ports > 1024


Addresses in `ip.addr==192.168.100.20`:
`Counter({'192.168.100.20': 4056, '192.168.100.10': 3025, '192.168.100.255': 82, 'ip.dst': 41, '192.168.100.11': 23, '224.0.0.252': 22, '192.168.100.12': 21, '224.0.0.22': 20, '239.255.255.250': 6, '192.168.100.18': 4, '255.255.255.255': 3})
`
