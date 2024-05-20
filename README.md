# Active Directory Home Lab

## Objective

The Active Directory Home Lab project creates a controlled domain environment to explore and understand the workings of Active Directory. This environment included the integration of Splunk, Kali Linux for penetration testing, and Atomic Red Team. The primary focus is to centralize and analyze logs within the SIEM (Splunk) by generating test telemetry to mimic attack scenarios. This hands-on project was designed to deepen understanding of domain environments, network security, and attack patterns while providing practical experience.

### Skills Learned

- Understanding of SIEM concepts and practical application.
- Analyzing and interpreting network logs.
- Ability to generate attacks.
- Knowledge of network protocols and security vulnerabilities.
- Critical thinking and problem-solving skills in Blue Teaming and general IT.

### Tools Used

- Security Information and Event Management (Splunk) system for log analysis.
- Network analysis tools (such as Wireshark) for capturing and examining network traffic.
- Telemetry generation tools (Crowbar, Atomic Red Team) to create realistic attack scenarios.
- Database of users promoted to a domain controller (Active Directory).

# Steps
HARDWARE RECOMMENDATIONS: Windows OS, 16 GB RAM, 250 GB Disk Space

Network Diagram: General Network Design and Topology.
- Green Dotted Lined: Indicates forwarding of data to splunk server.
- Dotted Lined: Indicates forwarding of data to splunk server.
- Red PC: Attacker.
- Regular PC: Target Machine.
  
![Screenshot 2024-05-19 211025](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/ff6f8853-8b06-44fb-a9d1-a28330b851b3)

### Install VirtualBox
https://www.virtualbox.org/wiki/Downloads
<br>
Follow the Setup Wizard and leave everything on default by clicking "Next" or "Yes" until you see "Finish". 
![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/84628c34-c703-4cc7-b9d0-0570e305255d)

### Create Windows 10 ISO Image
https://www.microsoft.com/en-us/software-download/windows10
<br>

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/5cca554c-5da3-4a0f-8225-c7a0e667cac9)

Click on the file to open the "Windows 10 setup".

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/2b0365f6-97a5-4684-b987-40750aa554d5)

