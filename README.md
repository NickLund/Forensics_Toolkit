# Forensics_Toolkit
IT566 Forensics Tool kit. List and descriptions of the tools we used in class.

### FIR (fast incident response)
#### Description
FIR (Fast Incident Response) is a cyber security incident management platform designed for agility and speed. It allows for easy creation, tracking, and reporting of cybersecurity incidents.
In the fields of computer security and information technology, computer security incident management involves the monitoring and detection of security events on a computer or computer network, and the execution of proper responses to those events. Computer security incident management is a specialized form of incident management, the primary purpose of which is the development of a well understood and predictable response to damaging events and computer intrusions.
FIR is for anyone needing to track cyber security incidents (CSIRTs, CERTs, SOCs, etc.). It’s was tailored to suit our needs and our team’s habits, but we put a great deal of effort into making it as generic as possible before releasing it so that other teams around the world may also use it and customize it as they see fit.

#### Scource URL
https://github.com/certsocietegenerale/FIR

### FTK
#### Description
Scans hard drives and images for data. Can find data that is deleted or otherwise thought to be lost. Using the imager software/add on, you can easily create an image of the hard drive. 

#### Personal Review and Notes
This is a great tool to use, as it is very simple to set up and use. You can stumble your way through the imaging process. 

#### Source URL to download:
https://accessdata.com/product-download/forensic-toolkit-ftk-version-7.0.0#product-downloads

### Wireshark
#### Description
Wireshark is a protocol/packet analyzer. It can break down network communications packet by packet. You can see TCP handshakes, SSL handshakes, see and inspect http traffic, see all the protocols, and much more. Very powerful tool. It can be overwhelming without practice, but over time, it becomes more simple to use with the correct filters and columns in place. 

#### Personal Review and Notes
I use this program nearly everyday for my job as a tech support engineer for proxy servers. I have fully customized my filter columns to be fully functional and efficient for my work. TTL, overal time (delta time is saved but hidden until needed), source and destination IP address, destination port, protocol, details, destination host name (http or ssl) and stream index. For my columns, see the file called 'export'

#### Source URL to download:
https://www.wireshark.org/download.html

### Volatility
#### Description
Volatility is an open source program for memory analysis.
#### Personal Review and Notes
I think I just had a hard time learning about it, and also I generally struggle with command line usage. It can be very powerful, but, I'm not quite sure how to use it all the way.

#### Source URL to download:
https://www.volatilityfoundation.org/releases

### ELK (Security information and event management)
#### Description
Elasticsearch, Logstash, and Kibana. Services for aggregating and presenting logs. 
#### Personal Review and Notes
I get the impression that this is similar it learning curve and usability to wireshark. Its pretty overwhelming and not very much instruction out there on how to use it. Kinda sink or swim. I cannot understand for the life of me how to find, configure, and read useful logs. 

#### Source URL to download:
Here is how to install it: https://github.com/NickLund/it366

### Netcat
#### Description
It is a network tool/utility for reading and writing to network connections. You can port scan/listen, transfer files, and other things. 
#### Personal Review and Notes
Just as all command line tools, they are a bit too powerful for me, and I feel a bit confused about how to use it. Once I think I get a grip on it, I can use it easily, I'll just need a bit more practice. Here is an example of a real use of it from my lab:

"First, move the compiled file (the result from the above directions) to the victim machine using netcat. Our victim’s IP address was 192.168.227.1. The port we used was 2222. The following commands will move the compiled file through Netcat.
```
sudo insmod lime-<version>-generic-pae.ko “path=/dump.mem format=lime timeout=0” 
```
(This first command pushes the file to netcat)
```
cat dump.mem | nc 192.168.227.1 2222
sudo dd bs=16M if=/dev/sda | nc 192.168.227.1 2222
```

Last, from the forensics workstation, set up a listener using the command
```
ncat -l 2222 > FileName.mem
```
(For Linux, this command is ``nc -l 2222 <FileName>.mem"``)


#### Source URL to download:
For windows you can download nmap which includes ncat here: https://nmap.org/download.html
For linux, you can just use apt.

### LiME (Linux Memory Extractor)
#### Description
It is used for volatile memory acquisition from Linux. It minimizes its interaction between user and kernel space processes during acquisition, which allows it to produce memory captures that are more forensically sound than those of other tools designed for Linux memory acquisition.
#### Personal Review and Notes
It is pretty simple to use, just load it on a seperate linux (not on machine to pull data), and then connect to the machine in question, then run the program. For instance, you will run these commands on the host machine to prepare it:
```
sudo apt-get install linux-headers-<kernel version>-generic-pae
sudo apt-get install build-essential
sudo apt-get install git
cd Downloads
git clone https://github.com/504ensicsLabs/Lime
cd Lime/src/
make
```
Then you will get the files:
```
sudo insmod lime-<version>-generic-pae.ko “path=/dump.mem format=lime timeout=0” 
cat dump.mem | nc 192.168.227.1 2222
sudo dd bs=16M if=/dev/sda | nc 192.168.227.1 2222
```

#### Source URL to download:
https://github.com/504ensicsLabs/Lime

### GNU DD
#### Description
It is used to convert and copy files. 
#### Personal Review and Notes
I used it once in a lab. 

### Snort
#### Description
Snort is a powerful tool used for analyzing packet captures and agregating them according them to predefined rules.
#### Personal Review and Notes
We used this several times to find malicious activity in very large packet captures. These were too large to sort through wireshark. We loaded up the commonly found viruses, or signatures of virus activity. It then found matches, and outputted simple, easy to read data on the data. 
#### Source URL to download:
https://www.snort.org/#get-started
See rules and preproc_rules for sample rules.

### tcpdump
#### Description
Prints out a description of packets on an interface. 
#### Personal Review and Notes
It is not as powerful as wireshark, but it is used on linux based machines, so it is useful for that, and is pretty quick. I am extremely biased in favor of wireshark. I once had to use a tcp dump at work and it was not helpful. I was disappointed. 
#### Source URL to download:
``apt-get install tcpdump``

### Autopsy
#### Description
Extremely powerful forensics tool. Free competitor to FTK. 
#### Personal Review and Notes
I personally used this, and it was good for finding many files, and it was organized in an easy to understand way. I could browse files by application or type. All the logs were together, and I could see them all. 
#### Source URL to download:
https://www.autopsy.com/download/
