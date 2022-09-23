



* Connect the SSD on to the embedded board.Get the Name, UUID and File System Type.

```
sudo blkid
```


Open the terminal, run the above command to see the name of the drive, its UUID(Universal Unique Identifier) and file system type.


<br>
<img src="https://github.com/Godson-Thomas/Automount-FS/blob/master/_1.png" width="700"><br><br>



First, you need to know the name of the drive that is going to be automatically mounted. For example, the name of the drive that is going to be automatically mounted on this example is _/dev/sdb9_.

Then we need to know its UUID and file system type. The UUID of _/dev/sdb9_ is _eb67c479-962f-4bcc-b3fe-cefaf908f01e_ and the file system of _/dev/sdb9_ is ext4 which is the standard file system in Linux.

* Make a Mount Point For Your Drive

 Make a mount point under /mnt directory. Enter the following command:
 ```
 sudo mkdir /mnt/<name-of-the-drive>

 eg. sudo mkdir /mnt/sdb9
 ```


 * Edit /etc/fstab File

 Run the following command to edit the _/etc/fstab_ file.
 ```
 sudo vi /etc/fstab
 ```

 We need to append one line of code at the end of the file. The format of this line of code is as follows:

**UUID= \uuid-of-your-drive\  \mount-point\  \file-system-type\  \mount-option\  \dump\  \pass**


Note: Add the following line to the end of _/etc/fstab_. Separate with Tab key

```
UUID=eb67c479-962f-4bcc-b3fe-cefaf908f01e  /mnt/sdb9  ext4  defaults  0  2
```

<br><br>
<img src="https://github.com/Godson-Thomas/Automount-FS/blob/master/_2.png" width="700"><br><br>

* Save and close the file
* Type the below command for auto mount.
```
sudo mount -a
```
* Check if it is mounted by typing the following command.

```
df -h
```




