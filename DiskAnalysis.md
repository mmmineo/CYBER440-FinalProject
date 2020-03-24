# Disk Analysis

Disks analyzed using Autopsy 4.14.0

**Note: Try Central Repository correlation**

### IT_2

IP Address:

#### Users

- admin
- Administrator
- DouglasAdams
  - MRCv120.exe in Desktop
- RoyTremmeman
  - NetworkMiner, MRCv120, all Network diagrams, Wireshark

#### Emails

Lots. Exported as .csv and parsed with Python

#### Recent Documents

These network diagrams show how the company has grown over the years. The interesting part is the most recent diagram, 12-10-19, was deleted for an unknown reason.

*6807-Network Diagram 7-20-2015.pdf*
![NetDia072015](./Screenshots/NetDia072015.jpg)

*6805-Network Diagram 4-15-2017.pdf*
![NetDia040517](./Screenshots/NetDia040517.jpg)

*6803-Network Diagram 12-10-2019.pdf*
![NetDi121019](./Screenshots/NetDi121019.jpg)

Below are the most current devices on the network.

*Network Table.docx*
![NetworkTabledocx](./Screenshots/NetworkTabledocx.jpg)

*Network Table.xlsx*
![NetworkTabledxlsx](./Screenshots/NetworkTablexlsx.jpg)

#### Interesting Programs

- NetworkMiner: Similar to Wireshark, but more likened to tcpdump
- MRCv120: Live M/W scanner? No installation?

---

### Mayor2_2

IP Address:

#### Users

- SoniaTheodore
- HelenJackson
- ShirleyAbdulla
- Administrator
- admin
- Guest

#### Emails

#### Recent Documents

Lots of "Board Meeting" PDFs

#### Interesting Programs

#### IOC
- HelenJackson's Desktop contains `RansomNote.txt` claiming system encryption and giving a bitcoin wallet number

---

### Mayor2_4



---

### SharedDrive

IP Address:

#### Commentary

Personal data should not be kept on Shared Drives where it is accessible and possibly writeable by an arbitrary user.

The same goes for HIPAA, FERPA, and other sensitive data. In this case, that is tax and police records.

*Are the cat pictures encrypted files or actually cats?*

#### Data Contained

Deleted giacobeville share within the Giacobeville domain contains numberous emails exchanged between many different people. 

#### IOC

---

### TaxOffice_1

VMDK instead of standard .EO1

---

### TaxOffice_2

- admin
- administrator
- Default
- MikeGold
- MillyBond

Users/MikeGold/Documents/  contains 42 images of cats
Users/MikeGold/Documents/ also contains Tax-info.xlsx
Users/MikeGold/Desktop/ contains more pictures of cats

---

### TaxOffice_4

- admin
- administrator
- Default
- MikeGold
- MillyBond

Users/MillyBond/Documents/Tax-info.xlsx contains a spreadsheet of tax information 
Users/MikeGold/Documents/Tax-info.xlsx contains the same spreadsheet

---

### Police1_1

#### Users

- ThomasFord
- administrator
- admin
- Guest
- Administrator

#### Emails

13,800+ on sqlite database, located at Users/ThomasFord/AppData/Roaming/Thunderbird/Profiles/4kydsg2w.default-release/places.sqlite-slack

#### Interesting Files

Tons of pictures of cats in the desktop, documents, downloads, and pictures locations.
