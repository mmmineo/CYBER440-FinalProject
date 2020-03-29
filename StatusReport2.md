# Status Report 1
Team 1
  - Brant Goings: **Network, Disk, Memory, Logs, BLUF**
  - Sarah Hume: **Logs**
  - Ryan Coe: **Disk**
  - Stephen Giacobe: **BLUF**
  - Parker Chambers: **Disk**
  - Matt Mineo: **Memory**

### Data Description BLUF ###

Provide a 1-slide BLUF perspective with your understanding of what has happened. Identify the structured analytic method that you're using to organize the evidence you've found. Remember to keep it at a high level, sufficient for the CEO of your client, but don't "dumb it down."

### Network Data ###
- Is your network data contiguous? If not, what does your network data cover? **Yes, the network devices are all found on the 192.168.100.0 subnet. See table for more details.**

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

- Does your network data cover all systems? If not, identify where in the network that you think the capture covers and what it doesn't cover. **See below diagrams and explanation**

These network diagrams show how the company has grown over the years according to IT_2 user RoyTremmeman. The interesting part is the most recent diagram, 12-10-19, was deleted for an unknown reason.

*6807-Network Diagram 7-20-2015.pdf*
![NetDia072015](./Screenshots/NetDia072015.jpg)

*6805-Network Diagram 4-15-2017.pdf*
![NetDia040517](./Screenshots/NetDia040517.jpg)

*6803-Network Diagram 12-10-2019.pdf*
![NetDi121019](./Screenshots/NetDi121019.jpg)

Below are the most current devices on the network according to IT_2 user RoyTremmeman.

*Network Table.docx*
![NetworkTabledocx](./Screenshots/NetworkTabledocx.jpg)

*Network Table.xlsx*
![NetworkTabledxlsx](./Screenshots/NetworkTablexlsx.jpg)

Based on analysis across Disks, Memory, Network, etc., the network data seems to cover all systems, although the diagrams don't seem to be specifically IP Address accurate.

- Do the services that are hosted on the systems make sense for the services that should be offered from those systems. **This is where the network captures differ from the provided network diagrams. See below.** 
  - **In the diagrams above, the Domain Controller (DC) is said to be 192.168.100.1, but during analysis we found that to be 192.168.100.10. Our reasoning is that 192.168.100.10 had ports 445 and 139 (SMB), 143 (IMAP), 88 (Kerberos), and 389 (LDAP) sourcing from it much more than any other port. These ports are indicative of a Windows Domain Controller running File Sharing on SMB, Mail on IMAP, and Active Directory on Kerberos and LDAP.**
  - **One peculiar machine was 192.168.100.12 which had 220 packets sourcing from TCP 80 (HTTP). This isn't very many packets in the long run, but it's worth noting as it's easy to transmit cleartext data over this insecure protocol**
  - **Another instance of similar proportion happened on 192.168.100.19 but over TCP 443 (HTTPS). This isn't as concerning unless an attacker were to get system-level access, in which case they could transmit malicious encrypted data across the network without being discovered.**

### Forensic Image Analysis ###
- What are those systems used for?
- What user accounts exist on each system?
- What do you know about the activities or actions of the user accounts prior to the incident?
- Are there any issues with the accounts that you have found? Are they all authorized? Do you know anything about their passwords?
- What software is installed on each system? Was there anything installed recently?
- Identify and explore common vectors of attack - phishing, malicious web pages, malicious software installations, etc.

### Memory Forensics ###
- Is each of the programs running on the system a normal process?
- Are any of the processes running abnormal?
- How much memory does each process take up? Is that a normal amount?
- What do you know about the code that is running?
- Consider spinning up similar systems to do a process-by-process comparison

### Log Files ###
- For each type of log entry - what systems contribute log entries?
- For each type of log entry - are these loge entries "normal" behavior?
- Are there any time gaps in your log files?
- Are there any unusual log entries? If so, what makes them unusual?

### IOCs ###
- Identify any initial findings
- Identify any preliminary IOCs that you have found.  Provide some statement of confidence of your analysis of those IOCs.

### Questions and Concerns ###
- Identify any questions you have for the client
- Identify any concerns or issues that your team has
