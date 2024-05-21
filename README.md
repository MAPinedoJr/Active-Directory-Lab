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


### Install Windows Server
https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server-2022 
Click Download ISO.
![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/60d7032f-d6c5-4ddd-bd81-8df52dd7ee76)

Fill out the fields and click Download now.

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/8f2472a0-7041-4aa1-aba2-8d27e9a99096)

Download 64 bit ISO.

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/4a3b40f9-cb0a-4533-acc9-459063b5c863)

On vitual box click New.

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/22083ba5-8438-4477-9ef3-99844b374ac1)

Fill out the name, use the ISO image you downloaded, and Skip Unattended Installation.

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/4ba5f5c5-2462-4e74-bb18-a08e7d0ef58e)

Give the machine 4 GB of RAM and 1 CPU.

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/ce45dacb-b071-4298-b666-a29c3182b2fe)

Leave Virtual Hard Disk on default and Click next. Click Finish.

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/3a46c9e8-3610-4fc8-9cd1-4dc2803b826e)

Once you start the machine, you should see the following, click next.

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/4b4c1342-fc19-4f21-8f8f-f8e940ec0e73)

Select Install now. 

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/cf985f81-d2d3-470e-8f5e-fb92a94ec3a3)

Select the follwoing OS and click next.

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/1d4a1a84-3b52-4dd3-b34c-e1bde65cafd2)

Select custom install.

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/378790d5-3bb3-4b58-b237-f408815e4a63)

Click next.

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/990ce376-347e-47d9-bbcf-e1a220a15fea)

Microsoft server should then begin installing.

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/050d21c3-72da-455d-8b34-cdeda102e07f)

After it has finished installing, create a super secure password and click finish.

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/5e671223-9242-4232-870d-729207ce03e9)

You will then be prompted to Press Ctrl+Alt+Delete. Insert this by going to Input > Keyboad > Insert Ctrl-Alt-Del.

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/b68ef758-c4b4-4360-a547-3a126c6fd58d)

Login using the password you set and you should see Server Manager once you login.

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/597a16f2-08fa-4586-9852-7ae88105922c)

![image](https://github.com/MAPinedoJr/Active-Directory-Lab/assets/168390763/8f77efa0-58e9-4c3b-b9cf-a0ff147c2ab9)





