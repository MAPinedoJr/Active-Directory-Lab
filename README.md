# Active Directory Home Lab

## Objective

The Active Directory Home Lab project creates a controlled domain environment to explore and understand the workings of Active Directory. This environment included the integration of Splunk, Kali Linux for penetration testing, and Atomic Red Team. The primary focus is to centralize and analyze logs within the SIEM (Splunk) by generating test telemetry to mimic attack scenarios. This hands-on project was designed to deepen understanding of domain environments, network security, and attack patterns while providing practical experience.

### Skills Learned

- Understanding of SIEM concepts and practical application.
- Analyzing and interpreting logs.
- Ability to generate attacks.
- Knowledge of network protocols and security vulnerabilities.
- Critical thinking and problem-solving skills in Blue Teaming and general IT.

### Tools Used

- Security Information and Event Management (Splunk) system for log analysis.
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

### Install Windows 10 Machine
#### Create Windows 10 ISO Image
https://www.microsoft.com/en-us/software-download/windows10
<br>

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/5cca554c-5da3-4a0f-8225-c7a0e667cac9)

Click on the file to open the "Windows 10 setup".

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/2b0365f6-97a5-4684-b987-40750aa554d5)

Select the second option and continue. 

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/4811e196-4597-4ac9-bed3-6f910aff76c6)

Use the recommended options and continue.

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/f731d317-c361-4293-9fc7-7f6d5228c159)

Select ISO file and continue. Save it anywhere you like.

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/c807a135-f48b-4ef8-a197-65ea0a7e41c1)

Open Virtual Box and Select "New".

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/22083ba5-8438-4477-9ef3-99844b374ac1)

Name the virtual machine and find the ISO image you downloaded for windows 10. Skip unattended installation.

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/1ee9648e-8517-4010-9fe7-fbd85c1f9df4)

Give the machine 4 GB RAM and 1 CPU. Continue.

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/c74e8b58-c15f-4183-811f-2c1e1b67ebce)

Leave everything on default for Virtual Hard Disk and continue. 

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/bb8a3adf-c5fc-40ab-aa32-e0296d7a1d72)

Click "Finish" on the Summary page.
<br>
Click on the green arrow to "Start" the machine. You should get the following windows 10 setup screen after starting.

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/419435c1-4bdb-44d5-bd93-0669825cbc33)

After clicking "Next", click "Install now".

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/f6694f37-23e2-43e6-9137-cab67a138834)

When prompted to Acvtivate Windows, click "I dont have a product key".

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/f2a3a475-80f3-4020-84c9-2b59b0da08b7)

Make sure to select "Windows 10 Pro".

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/a1430c80-9e94-4ed0-a9ce-f65b7109eee4)

Accept the license terms and then select "Custom: Install...".

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/9f28001c-166f-467e-bfe2-aa8afae192d5)

CLick "Next" and it should begin installing.

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/622df971-609e-4067-bf53-7fb2bf0569f6)

Follow the windows 10 setup and choose an offline account. You will have to setup a password for the machine. Skip through most customizations.

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/8a978712-009e-40ad-a479-7716a2cae26d)

You will then boot into the Windows 10 desktop environment.

### Install Kali Linux
https://www.kali.org/get-kali/#kali-virtual-machines 
<br>

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/099a7a22-b61e-43d2-bcf7-c69dde3ab399)

Download and install 7-zip.

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/cc21b4fc-7c6d-4e85-9fa6-dc526dbf910f)

Right Click kali linux file and extract with 7-zip.

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/83528aba-da4d-4b75-a730-60d4f86f7404)

Double Click Kali Linux .vbox file to import it into virtual box.

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/4bebf8e1-cec3-42ff-b268-4da85e46a875)

Kali should be imported. If you click the green start arrow, log in using default credentials: Passwd: "kali" User: "kali".

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/407638c5-9b4b-47fd-a551-d5845c2fa929)







