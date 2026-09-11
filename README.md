# <img width="15" height="23" alt="Padlock" src="https://github.com/user-attachments/assets/5bddf626-c025-41a5-9be9-86772ba08f50" />  Cybersecurity Lab Envirnment Setup

1. Project Overview
   
This Cybersecurity Lab Setup project focuses on building a safe, isolated, and virtualized environment to simulate cyberattacks, analyze malware, perform vulnerability assessment and test defensive security controls.
The lab is setup and configured on a Private Virtual Network so that additional machines can be added later and used as targets for authorized security testing.


3. Project Objectives

The main objectives of this project are to:

Installation and configuration of VirtualBox
Install/import Kali Linux as a virtual machine.
Create a private NAT Network for the cybersecurity lab.
Configure network connectivity for Kali Linux.
Assign a consistent IP address to the Kali VM.
Verify network connectivity and DNS resolution.
Take a clean VM snapshot for recovery.
Document the complete setup process.
Prepare the environment for future cybersecurity projects.

3. # Purpose of the Lab

The lab provides an isolated and controlled environment for cybersecurity learning and authorized security testing.

It can be used for activities such as:

Network reconnaissance
Port scanning
Vulnerability assessment
Packet analysis
Web security testing
Exploitation practice
Security-tool experimentation

4. Lab Setup Procedure

Step 1.	Download and Install 7-Zip
	7-Zip was installed to extract the Kali Linux virtual-machine package, which may be distributed as a .7z archive
Tool:	7-Zip

Step 2.	Download and Install VirtualBox
	VirtualBox was downloaded and installed as the hypervisor.

Step 3.	Create the Nat Network
	A dedicated Nat Network was created in VirtualBox
	The configuration is shown in the picture below.
	IPv4 Prefix: 10.0.0.0/24
