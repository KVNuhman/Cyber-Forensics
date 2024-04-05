# CYBER FORENSICS EXPERIMENT

### Shibily Nuhman K.V.
### CB.SC.P2CYS23022

### Investigating a suspicious USB pendrive found at a crime scene. The forensic team needs to acquire evidence from the pendrive while ensuring the integrity of the data. Using the dd and dc3dd commands, create a forensic image (.img) file of the pendrive. Additionally, generate a SHA-256 hashfile for the image file to verify its integrity. Finally, wipe the pendrive using the disk wipe pattern 00011 to prevent any potential data leakage.

* We would insert our usb drive and enter the command fdisk –l
  ![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/3ac725d1-0a34-49ff-8c95-a3cfff521819)
* We create a disk image of inserted usb drive
  `dd if=/dev/sdb1 of=disk.img`
  ![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/aa7dc9a9-b049-40a4-a371-481d6a58caa8)
* We verify the created disk image file and delete it.
  ![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/e9dd44f7-bcd5-401e-9638-55f201c1c77c)
* We can also create disk image by explicitly specifying block size and adding error handling to it.
  ![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/0eaa52c9-6338-407f-a553-6bdc380e8550)

## DC3DD

* Install DC3DD
  ![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/80649593-4295-4c01-93d9-8a0098790c3c)
* Manual page of DC3DD
  ![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/b2ab2759-f24d-4f80-906b-32c0857c4f74)
* Again we have to enter fdisk –l command and insert usb drive.
  ![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/3ac725d1-0a34-49ff-8c95-a3cfff521819)
* We have to split usb with the help of dc3dd tool
  `dc3dd if=/dev/sdb hash=sha256 log=split_usb ofs=test.img.000 ofsz=500M`
