# sFTP guideline

## Introduction

Secure File Transfer Protocol (SFTP) is a file protocol for transferring large files over the web. It builds on the File Transfer Protocol (FTP) and includes Secure Shell (SSH) security components.

Secure Shell is a cryptographic component of internet security. SSH and SFTP were designed by the Internet Engineering Task Force (IETF) for greater web security. SFTP transfers files security using SSH and encrypted FTP commands to avoid password sniffing and exposing sensitive information in plain text. Since the client needs to be authenticated by the server, SFTP also protects against man-in-the-middle attacks.

SFTP can be handy in all situations where sensitive data needs to be protected. For example, a Relecov user for encrypting the upload of sequencing data and sensitive metadata.

This protocol can be launched either as a command line or through a graphical user interface (GUI). In the first type of setup, the user has to type in specific command lines to generate the SFTP protocol, usually in a Linux environment. The latter option, that we recommend, makes use of a program that abstracts the use of SFTP visually for end users.

For this purpose, we recommend (Filezilla)[https://filezilla-project.org/]. This software allows to connect to a FTP server, download and upload files and all with a friendly graphic layout.

## Connectiong to a server

Each Relecov-user has its own ID and password with they might connect to Relecov sFTP server. As example:

```
 Server: sftprelecov.isciii.es
 Username: COD-MAD-2100
 Password: 12345
```

You cand use the quickconnect bar for establishing the connection, like que figure X.

![Figure 1](images/figure1.PNG)






- fastq
- metadata
- mdsum

There are several options to connect by sFTP and we recommend use the software (Filezilla)[https://download.filezilla-project.org/client/FileZilla_3.60.1_win64_sponsored2-setup.exe]. This software is free