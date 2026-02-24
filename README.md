# NpingSpoofingAttack

Using Nping tool: Understand Spoofing Attacks

In an IP or MAC spoofing attack, an attacker sends packets from a false (or “spoofed”) IP or MAC source address in order to disguise itself. Nping is an open-source tool and it allows users to generate network packets of a wide range of protocols, letting them tune virtually any field of the protocol headers. While Nping can be used as a simple ping utility to detect active hosts, it can also be used as a raw packet generator for network stack stress tests, ARP poisoning, Denial of Service attacks, route tracing, and other purposes. Nping is a part of NMAP. I have nmap software and Wireshark installed and those are the software I would use for this project. 

I would check my computer IP and MAC address by Dos command, so I ran the command “ipconfig -all”
 <img width="800" height="214" alt="image" src="https://github.com/user-attachments/assets/819751ef-bc52-4bd4-8d1f-7d2f4efc00b9" />
<img width="709" height="232" alt="image" src="https://github.com/user-attachments/assets/454f47cc-9f4c-433c-84a3-100447d205f5" />

 

Then I ran the Dos command nping -S 99.99.99.1 www.cuny.edu. This command sets the source IP address as 99.99.99.1, and sends ICMP to the target.
 <img width="697" height="300" alt="image" src="https://github.com/user-attachments/assets/f569e729-2277-4817-9ccd-3b43ef9dd1e6" />


I then opened Wireshark to verify that the source IP has been changed. To capture the packets: I needed to start to capture packets on Wireshark first, then run the Dos command in  the previous step. After it is done, I stopped the capture on Wireshark and could see the source IP address which is the sender IP packets has changed to 99.99.99.1
 <img width="812" height="297" alt="image" src="https://github.com/user-attachments/assets/e769f3a1-4c7b-4996-b9d1-1d186ac47933" />


I could use the Dos command nslookup 128.228.254.200, and it shows that this IP belongs to web.CUNY.edu.
 <img width="441" height="167" alt="image" src="https://github.com/user-attachments/assets/10957404-d167-4b7d-ab5b-3f682772301d" />


On Dos command, I ran the command nping –source-mac 00:01:01:01:01:08 –tcp -p 80 scanme.nmap.org. This command sets the source MAC (physical) address as 00:01:01:01:01:08, and it sends the TCP packet to its http port.
 <img width="745" height="436" alt="image" src="https://github.com/user-attachments/assets/a63c0e86-d9ec-46e4-b91f-18c99aaa0c93" />
<img width="679" height="178" alt="image" src="https://github.com/user-attachments/assets/a5ac9cb8-a4b2-4c0c-8cae-221d59d94e03" />

 

On Wireshark I could verify that MAC address changed in the ethernet layer in the bottom panel.
 <img width="774" height="160" alt="image" src="https://github.com/user-attachments/assets/4d0a1586-aeb9-4610-991a-23e6b8d00727" />


Here I’m going to use spoofed IP as 88.88.88.88. Spoofed MAC as 00.02.02.02.02.02. Checking my information first.
 <img width="577" height="225" alt="image" src="https://github.com/user-attachments/assets/05e7735c-a1d3-476b-b492-3d0b6facd88f" />


Setting the IP address to the spoofed IP 88.88.88.88
 <img width="772" height="344" alt="image" src="https://github.com/user-attachments/assets/7b3b7994-aa70-49ad-8ade-e37c47ae1a60" />


Confirming the source IP has changed. 
<img width="691" height="364" alt="image" src="https://github.com/user-attachments/assets/8bb9c647-e939-4a20-9498-cbf944aec891" />
 

Changing the the MAC address to the spoofed information. 
 <img width="717" height="332" alt="image" src="https://github.com/user-attachments/assets/ac3e2f2f-0c4f-4966-bdf0-6cd76be478e5" />


Confirmation of spoofed MAC address in the bottom panel 
<img width="763" height="136" alt="image" src="https://github.com/user-attachments/assets/b29286f1-0729-4148-92c9-b91f0e434e90" />
 


