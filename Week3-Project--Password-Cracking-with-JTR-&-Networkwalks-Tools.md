<p align="center">
  <img width="662" height="366" alt="JTR" src="https://github.com/user-attachments/assets/68359fdf-59ae-497e-9d15-8c91ee544141" />
</p>

# <h1 align="center"> PASSWORD CRACKING WITH JTR </h1>

## Overview
**John the Ripper (JTR)** is a popular password cracking tool used by security professionals to test how strong
passwords are. It started as a tool for Unix systems but now works on Windows, Linux, and Mac. It can
check many types of password hashes and also unlock password protected files like PDF, ZIP, and Office
documents.

Johnny is the graphical version of John the Ripper. It gives a simple point and click screen, so beginners can
use JTR without typing long commands. Both tools are widely used in security testing and learning labs to
understand password safety.

In this lab task you will use JTR John and JTR Johnny to recover the password of a protected PDF file. This
exercise helps you learn how password cracking works and why it is important to use strong passwords for
protection.

## Objectives
  * Installation of John the Ripper
  * Extraction of Hash ID of locked/proteced files
  * Cracking the locked filed password

## Tools Used
| S/N | Tool | Function |
|-----|------|----------|
| 1   | John the Ripper | It is the main tool and serves as where **John.exe** can be selected for Johnny to be functional |
| 2   | Johnny GUI | It is a graphical version of JTR that can be use without writing any code |
| 3   | Online Hash ID Cracker | It is used to extract Hash ID file that Johnny will crack to extract real password |
| 4   | Passworded/Encrypted PDF files; 1-3 files | These are protected files that were cracked |

## Procedures
### <sub> Step 1.
1. Download John the Ripper from their official website
<img width="1031" height="556" alt="ed" src="https://github.com/user-attachments/assets/f555978f-f423-47b8-9b77-ac2ed8995a42" />

### <sub> Step 2.

##### 1. Download and install Johnny GUI from their official website
<img width="753" height="493" alt="Installind JTR" src="https://github.com/user-attachments/assets/104029a5-1d1a-4dca-b455-fa944af38d56" />

**Johnny GUI installed**

<img width="376" height="187" alt="John installed" src="https://github.com/user-attachments/assets/ef3c1036-ac42-4eb3-8b5a-fd1b2a02a3f4" />

##### 2. After installation, Open Johnny
##### 3. Click on Settings and Browse
<img width="892" height="470" alt="sett" src="https://github.com/user-attachments/assets/539d4829-a115-49be-9d15-fded6fe861b9" />

##### 4. Select John.exe from JTR CLI downloaded
   <img width="1066" height="767" alt="Adding John exe" src="https://github.com/user-attachments/assets/89e2b922-4be4-436b-920e-6e48af14d090" />


**John.exe file is located in the folder as shown in the image below**

<img width="961" height="381" alt="Aft" src="https://github.com/user-attachments/assets/2bbd7b71-0c13-42c5-b001-3da494dba61b" />

### <sub> Step 3.
##### 1. Open OnlineHashcrack.com, click browse to select your protected pdf files and upload.
<img width="1089" height="518" alt="Upload the protected pdf" src="https://github.com/user-attachments/assets/e336a71d-98e6-457f-b000-ce86645d1478" />

##### 2. Copy the Output and save it as txt file
<img width="1147" height="517" alt="copy the hash ID" src="https://github.com/user-attachments/assets/626b6647-7435-44de-9b28-ae5174582975" />

##### 3. Add Password file **(Hash ID)** saved as txt file
<img width="871" height="546" alt="add passfile" src="https://github.com/user-attachments/assets/cd1570f4-9254-4a96-befd-5f215354c6ac" />

##### 4. Click on Start new attack to generate the real password and copy it to open the protected pdf files as shown below.

**img1: Password generated** 
<img width="896" height="586" alt="Add password file" src="https://github.com/user-attachments/assets/e974f075-930c-4a23-a08f-7d131af153b2" />

**img2: Open the locked PDF and paste the copied password**
<img width="1140" height="549" alt="pdf1 " src="https://github.com/user-attachments/assets/857c5862-8c44-4917-bc79-c0745dc6342f" />

**img3: The PDF1 Unlocked**
<img width="1344" height="645" alt="PDF1 UNLOCKED" src="https://github.com/user-attachments/assets/2ab7e85a-da4c-4fd0-9b2a-a87761d9f46e" />

**img4: PDF2 Unlocked**

<img width="574" height="558" alt="PDF2 Unlocked" src="https://github.com/user-attachments/assets/20451b6c-43b4-4712-a76b-6d379617d549" />

**img5: PDF3 Unique Password**
<img width="868" height="401" alt="PDF3 PASSWORD" src="https://github.com/user-attachments/assets/d9aaa3c1-4db0-4b61-903e-1e4027417158" />

**img6: PDF3 Unlocked**
<img width="815" height="578" alt="PDF3 Unlocked" src="https://github.com/user-attachments/assets/79de7875-2cb6-4f53-b8a4-1fb6e45a2a7d" />

<p align="center">
  <img width="602" height="233" alt="nw" src="https://github.com/user-attachments/assets/5f973ff6-44db-493f-b65b-8d38edc544e2" />
</p>
# <h1 align="center"> PASSWORD CRACKING WITH NETWORKWALKS TOOLS </h1>

## Overview
Password cracking is the process of recovering a password from stored data or a protected file. Security
professionals use it to test how strong a password is and to show why weak passwords are risky. If a
password is short or common, it can be found quickly, which proves the need for strong passwords.

Many files like PDF, ZIP, and Office documents can be locked with a password. When a file is locked, its
password is stored in the form of a hash. A hash is a scrambled value that represents the password. To
recover the password, we first take out this hash from the file, and then run it through a cracking tool that
tries different words until it finds a match.

In this lab you will use two free online tools made by Networkwalks. First you will use the Hash Calculator
to take the hash out of a locked PDF file. Then you will use the Password Cracker to find the real password
from that hash. Both tools run in your web browser, so you do not need to install anything.

This lab helps you understand how password cracking works step by step and why strong passwords are
important for protection.


## Objectives
  * Extraction of Hash ID of locked/proteced files using Networkwalks Hash Calculator
  * Cracking the locked filed password using Networkwalks Password Cracker

## Tools Used
| S/N | Tool | Function |
|-----|------|----------|
| 1   | Networkwalks Hash Calculator | It is web based software that can work on any laptop to extract Hash ID. It is easy to use.  |
| 2   | Networkwalks Password Cracker | It is also a web based software which is use to crack hasd ID and generate the real password |
| 3   | Passworded/Encrypted PDF files; 1-3 files | These are protected files that were cracked |

## Procedures
##### 1. Open Networkwalks Hash Calculator in the web browser
Click this link https://networkwalks.com/hash-calculator/ to open **Networkwalks Hash Calculator**

<img width="1124" height="605" alt="Networkwalks Hash Calculator" src="https://github.com/user-attachments/assets/4857cb10-3262-4850-86fe-e94e80ea885f" />

##### 2. Locate the locked PDF file and upload it
<img width="1174" height="574" alt="nw2" src="https://github.com/user-attachments/assets/d4e47683-3ddd-4c1b-9426-8b47fbf4e2a0" />

##### 3. Copy the Hasd ID value starting from $pdf$.
<img width="918" height="513" alt="copy" src="https://github.com/user-attachments/assets/2f9b4fc2-bf7b-41e7-b37e-fe10b15b7311" />

##### 4. Open Networkwalks Password Cracker in the web browser
Click the this link https://networkwalks.com/password-cracker/ to open Networkwalks Password Cracker
<img width="1083" height="567" alt="Networkwalks Password cracker" src="https://github.com/user-attachments/assets/d987b175-74ce-408f-a0e9-4bb892fbca55" />

##### 5. Paste the Hasd ID value into Networkwalks Password Cracker and start cracking. 
It will try different passwords untill it finds a match.
<img width="931" height="573" alt="nw3" src="https://github.com/user-attachments/assets/d0f0dc71-2fc7-4d03-9da0-ed09972c7c7d" />

##### 6. Be patient for the tool to finish.
It is going to display the cracked password on the screen
<img width="1134" height="607" alt="PDF1 pwd unlocked by NetPwdCracker" src="https://github.com/user-attachments/assets/8519c102-fbf7-4a15-96b3-4019770ba0cb" />


##### 2. Copy the Output and use it to open the locked PDF files.
It is going to give you the same resulf after unlocked, just as the JTR
<img width="1140" height="549" alt="pdf1 " src="https://github.com/user-attachments/assets/911ca53d-d18c-4f75-a291-699d37f77395" />





