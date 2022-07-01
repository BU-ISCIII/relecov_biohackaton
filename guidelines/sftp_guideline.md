# sFTP guideline

## Introduction

Secure File Transfer Protocol (SFTP) is a file protocol for transferring large files over the web. It builds on the File Transfer Protocol (FTP) and includes Secure Shell (SSH) security components.

Secure Shell is a cryptographic component of internet security. SSH and SFTP were designed by the Internet Engineering Task Force (IETF) for greater web security. SFTP transfers files security using SSH and encrypted FTP commands to avoid password sniffing and exposing sensitive information in plain text. Since the client needs to be authenticated by the server, SFTP also protects against man-in-the-middle attacks.

SFTP can be handy in all situations where sensitive data needs to be protected. For example, a Relecov user for encrypting the upload of sequencing data and sensitive metadata.

This protocol can be launched either as a command line or through a graphical user interface (GUI). In the first type of setup, the user has to type in specific command lines to generate the SFTP protocol, usually in a Linux environment. The latter option, that we recommend, makes use of a program that abstracts the use of SFTP visually for end users.

For this purpose, we recommend (Filezilla)[https://filezilla-project.org/]. This software allows to connect to a FTP server, download and upload files and all with a friendly graphic layout.

## Connectiong to Relecov server

Each Relecov user has its own ID and password with they might connect to Relecov sFTP server. As example:

```
 Host: sftprelecov.isciii.es
 Username: COD-MAD-2100
 Password: 12345
 Port: 50122
```

You can use the quickconnect bar for establishing the connection, like the figure 1.

![Figure 1](images/figure1.PNG)

Enter the hostname into the quickconnect bar's *Host*: sftprelecov.isciii.es, the username into the *Username*: COD-MAD-2100, the password into the *Password*: 12345 as well as *Port*: 50122. Now click on *Quickconnect*.

FileZilla will now try to connect to the server. If all works well, you will notice that the right "column" switched from Not connected to any server to displaying a list of files and directories.

## Navigating and window layout

In figure 2, we can note the FileZilla layout. 

![Figure 2](images/figure2.png)

We explain a quick introduction:
- Below the toolbar (1) and quick connect bar (2), the message log (3) displays transfer and connection related messages.
- Below, you can find the file listings. The left column (local pane, 4) displays the local files and directories, i.e. your local PC files. The right column (server pane, 5) displays the files and directories on the Relecov server you are connected to. Both columns have a directory tree at the top and a detailed listing of the currently selected directory's contents at the bottom. You can easily navigate either of the trees and lists by clicking around like in any other file manager. At the bottom of the window, the transfer queue (6) lists the to-be-transferred and already transferred files.

## Transferring files

Now we might upload the files required for the Relecov platform:

```
- fastq.gz
- metadata.xlsx
- mdsum.md5
```
First, the **fastq data**. We need the raw data and in ```.gz```compressed format with the correct sample name. We remind to only use alpha-numeric characters and if you need to separate names, we strongly recommend ```_``` character. Second, the metadata in ```.xlsx``` format. Lastly, ```mdsum.md5 file```. This is a checksum file used to verify the integrity of a upload/downloaded file. It stores a hash code for every fastq file, which is created from an algorithm based on the number of bits in the file.

## Uploading

First - in the local pane - bring the directory into view which contains data to be uploaded to Relecov server (e.g. *fastq.gz, metadata.xlsx and mdsum.md5*). Now, navigate to your specific target directory on the server (using the server pane's file listings). To upload the data, select the respective files and drag them from the local to the remote pane. You will notice that the files will be added to the transfer queue at the bottom of the window and soon thereafter they were uploaded to the server. The uploaded desired files should now be displayed in the Relecov server content listing at the right side of the window.

![Figure 3](images/figure3.png)

> Note: If you don't like using drag-and-drop, you can also right click on files/directories (in the lower local pane) and select *Upload* to upload them - or simply double-click a file entry (this does not work for directories).

## Downloading

Downloading files, or complete directories, works essentially the same way as uploading - you just drag the files/directories from the remote pane to the local pane this time, instead of the other way round.

> Note: In case you (accidentally) try to overwrite a file during upload or download, FileZilla will by default display a dialog asking what to do (overwrite, rename, skip...).

## FAQs

- **How do you name the samples?**
Check always the samples names before upload them. Always use alphanumerical and *_* to separate the words you want to include and compressed format *.gz*. Pair reads must be signaled with a *R1* and *R2* respectively. As an example for pair end: *COD_MAD_2100_1_R1.fastq.gz* and *COD_MAD_2100_1_R2.fastq.gz*.