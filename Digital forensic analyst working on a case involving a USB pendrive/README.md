## Imagine you're a digital forensic analyst working on a case involving a USB pendrive suspected to contain crucial evidence. Detail the steps you would take to acquire the evidence and recover files from the pendrive using the following tools: Guymager for creating a dd file, and Foremost for file recovery. Explain each step of the process, from connecting the pendrive to your forensic workstation to generating a dd file using Guymager, and then recovering files using foremost.

Insert the pendrive and it's seen that the pendrive has a folder and two images. 

![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/d0db27ab-fa7c-4303-bfbe-414033e926c5)

Delete one of the image for example **firewatch.jpg**.

![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/235f8b4b-08b0-472f-bd51-2a48f2d55994)


## Guymager for creating a dd file

Now we run `guymager` in our Kali Linux system. To run this tool we simply use `sudo  guymager` command in our terminal window. It opens up a GUI were we can select the disk we want to create a copy of and then click on it and click **Aquire image**.

![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/a6593650-c496-4e21-b6a1-237878d015c0)

Here we can choose the file format and provide the case number and evidence number, examiner, descriptions and notes. Here we can also choose the image directory. We can also split the size of disk. We can calculate MD% and SHA1 and SHA-256. Then we must check the verification process, because if the image acquisition was not valid then it can't be an evidence. So verification is a good habit. Here we have done everything, and set the acquired image directory in our desktop, and we did not used the split image because we are not acquiring large image. Following screenshot shows the process.

![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/9a840abf-19ef-44a3-9dac-e3cfdff1cf8f)

Then we just click on start option and the process will started.

![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/c192a074-ad98-47d0-bfe4-c1720c858a73)

After finishing this process we will get a dd image file in our Desktop.

![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/bb0b3014-f93a-4f50-afcc-0520a2834c2e)

## Foremost for file recovery

Now we will use dd image to recover the image by using Foremost tool. To have a better understanding of Foremost and the switches used, try browsing the Foremost System Manager's Manual.This can be done by entering the following command: `man foremost` 

![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/8fd00f9f-4f98-46ba-91b8-481d5ead69dc)

The syntax for using Foremost is as follows: `foremost -i (forensic image) -o (output folder) -options` 

To recover the jpg image from from the dd image file, use the following command syntax: `foremost -t jpg -i <input_file> -o <output_directory>`

> `-t jpg`: This option specifies that Foremost should only recover JPG (JPEG) files.
> `<input_file>`: Replace this with the path to your dd image file.
> `<output_directory>`: Replace this with the directory where you want the recovered JPG images to be saved.
> This command will instruct Foremost to scan the dd image file for JPG images and recover them to the specified output directory

![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/065b17f8-8297-40ab-8c81-346f7de216f0)

Now go to the Recover folder in Desktop and there will be a folder called jpg, inside both the images including the deleted image is present. So the deleted image is successfully recovered.

![image](https://github.com/KVNuhman/Cyber-Forensics/assets/46161259/d38f6dd2-aed5-43d0-a776-91d6d4ac1101)

