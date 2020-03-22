# Log Analysis

How many log entries do you have? 89,719
```
def logcount():
    count = 0
    for file in filenames:
        with open(file) as currentcsv:
            csvreader = csv.reader(currentcsv)
            for line in csvreader:
                count += 1
    print(str(count))
```

What are the date/time ranges of the logs?
- Begins: 2020-02-28 15:06:25.815
- Ends: 2020-03-03 13:29:34.351

Describe the types of log entries you have -- what systems generated the log entries? IMAP Mail Server

Describe the log file aggregator - ELK Logging is a Linux-based aggregator

Identify any initial findings
- GET/SENT for hundreds of UID flags
- Most traffic sourcing from .21
- Source IPs: 192.168.100.21 192.168.100.10 192.168.100.11 192.168.100.14 192.168.100.13 192.168.100.16 192.168.100.18 192.168.100.17

**Mail Domain:** giacobeville.com

**Users:**
2/28
* DavidMcFarlane@Giacobeville.com
* DouglasAdams@giacobeville.com
* HelenJackson@Giacobeville.com
* MargaretMartinez@giacobeville.com
* michaelscott@giacobeville.com
* MikeGold@Giacobeville.com
* MillyBond@Giacobeville.com
* RonSwanson@giacobeville.com
* RoyTenneman@Giacobeville.com
* ShirleyAbdulla@giacobeville.com
* soniatheodore@giacobeville.com
* ThomasFord@giacobeville.com

## Elk Logs ##

## hmailserver_2020-02-28.log ##
**Source IPs:**
* 192.168.100.21
* 192.168.100.10
* 192.168.100.11

## hmailserver_2020-02-29.log ##
**Source IPs:**
* 192.168.100.21

## hmailserver_2020-03-01.log ##
**Source IPs:**
* 192.168.100.21
* 192.168.100.11

## hmailserver_2020-03-02.log ##
**Source IPs:**
* 192.168.100.21
* 192.168.100.11
* 192.168.100.14
* 192.168.100.13
* 192.168.100.16
* 192.168.100.18
* 192.168.100.17

## hmailserver_2020-03-03.log ##
**Source IPs:**
* 192.168.100.21
* 192.168.100.14
* 192.168.100.11
