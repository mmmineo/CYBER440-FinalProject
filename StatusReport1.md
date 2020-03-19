# Status Report 1
Team 1
  - Brant Goings: **Network, Disk, Memory**
  - Sarah Hume: **Logs**
  - Ryan Coe: **Disk**
  - Stephen Giacobe:
  - Parker Chambers:
  - Matt Mineo: **Memory**

### Data Description BLUF

The client provided our team with ~4 days of network traffic data, 8 disk images, 7 memory dumps, and about 90,000 log events. All of this data resides within the client's LAN.

Network analysis shows large amounts of traffic travelling between the assumed Domain Controller at 192.168.100.10 and all other hosts on the network.

Disk image analysis shows large amounts of PII on the network's shared drive.

Memory dump analysis shows _possibly malicious processes_

Log analysis shows purely IMAP mail traffic travelling between 192.168.100.21 (mail server?) and other hosts.

### Network Data
1. How many months/weeks/days/hours/minutes worth of network data do you have? **4 days, 7 hours, 45 minutes and 55 seconds**
2. How many packets? **12,315,047** _Note: "Killed" exception thrown on 02-27-2020_1.4_
  ```
  def countpack():
      counter = 0
      for name in filenames:
          os.system("sudo tshark -r " + name + " > tempfile.txt")
          with open("tempfile.txt") as file:
              for line in file:
                  counter += 1
      print(str(counter))
  ```
3. What times - beginning and ending?
  - Begins: **Feb 28, 2020 05:16:18.989733000 EST**
  - Ends: **Mar 3, 2020 13:02:13.407194000 EST**

### Forensic Image Analysis
1. How many different systems do you have forensic images for? **8**
2. Verify the hashes provided, or provide a hash of the image you received **See table**
3. What are those systems used for? **See table**
4. What user accounts exist on each system? **See table**
5. What other stuff were you provided? **A .zip of ShareDrive_4?**

System        | Purpose                         | User Accounts                                    
------------- | ------------------------------- | ------------------------------------------------
IT_2          | Network Analysis and Topologies | admin, Administrator, DouglasAdams, RoyTremmeman, Guest
Mayor2_2      |                                 | SoniaTheodore, HelenJackson, ShirleyAbdulla, Administratror, admin, Guest
Mayor2_4      |                                 |
Police1_1     |                                 |
ShareDrive_1  | Means of sharing office data    |
TaxOffice_1   |                                 |
TaxOffice_2   |                                 |
TaxOffice_4   |                                 |

System        | SHA256 Hash
------------- | ----------------------------------------------------------------
IT_2          | AE7F452E833FE73CBF47FE02004AAEC2FE31D9EE1958D3774B557DC565E3D809
Mayor2_2      | A2DF12A14DA8CC43736145FAEDAA56C91461F93BE2231BCE9DFB1AD9CD9196A7
Mayor2_4      | B4B124447C039F8B78835DDDBFEF0D9966D16A95B060D0FF99A4475CE064F630
Police1_1     | E06C600C851F54A3164EF1F04BF25C04393A06FA407760696539617DBF7EC469
ShareDrive_1  | B12CF8F1937CC9321AC721C8FB1CB0A15D853E3533E355EF0342CBF3A3E954FD
TaxOffice_1   | 77071E2BBAC8776CFE21540537DE9D1FB4CC2BB06A50BCE6F67F916F235A0F41
TaxOffice_2   | DD5D6948DE376321B8CCBE74DAAF31E6DACC2BD5546C352F7EB607BBFD737A3A
TaxOffice_4   | 3A0CD0EB6583C8AFC85E947BBDCD52D38E3268FE1217027B19E10D16543BBA45

### Memory Forensics
1. Which systems do you have a memory capture for? **See table**
2. What operating systems are each system? **See table**
3. What times/days were the captures completed? **See table**

System      | OS         | Date/Time
----------- | ---------- | ---------
IT_2        | Win7SP1x64 | 2020-03-01 19:54:10 UTC+0000
Mayor1_3    |    |
Mayor1_4    |    |
Mayor2_3    |    |
Mayor2_4    | Win7SP1x64 | 2020-03-03 17:58:51 UTC+0000
WinServer_1 |    |
Winserver_3 |    |

### Log Files
1. How many log entries do you have? **89,719**
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
2. What are the date/time ranges of the logs?
  - Begins: **2020-02-28 15:06:25.815**
  - Ends: **2020-03-03 13:29:34.351**
3. Describe the types of log entries you have -- what systems generated the log entries? **IMAP Mail Server**
4. Describe the log file aggregator - **ELK Logging is a Linux-based aggregator**
5. Identify any initial findings
  - **GET/SENT for hundreds of UID flags**
  - **All traffic sourcing from .21? _Need to confirm_**

### Identify any preliminary Indicators of Compromise
  - **_Unknown_**

### Questions and Concerns
1. Identify any questions you have for the client
2. Identify any concerns or issues that your team has
