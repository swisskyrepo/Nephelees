# Nephelees

> Néphélées (Νεφήλαι, Nephḗlai) : cloud nymphs greek - also a NTDS cracking tool abusing Google Colab 

<p align="center">
  <img src="https://github.com/swisskyrepo/Nephelees/raw/main/img/logo.jpg?raw=true"><br>
  <a href="https://colab.research.google.com/github/swisskyrepo/Nephelees/blob/main/google_colab_hashcat.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>
</p>


Most of the credits are due to @mxrch and @ShutdownRepo. This repository is mostly a rework of their scripts, head over to the [References](#references) for more informations.

## Quick Start

0. Open the `ipynb` file by clicking on the button **Open in Colab**
1. Select **Runtime**, **Change runtime type**, and set **Hardware accelerator** to **GPU**.    
2. Select **Runtime**" and **Run all"** !
3. On your local machine, run [hashonymize](https://github.com/ShutdownRepo/hashonymize) to anonymize your hash lists
4. Upload your anonymized hashes list on the colab `!wget http://yourip:yourport/yourfile` or with the upload button
5. Install requirements (hashcat + wordlists + rules)
6. Run hashcat commands
7. Recover the .pot file from the Google Colab `!curl --upload-file ~/.hashcat/hashcat.potfile http://yourip:yourport/` or download the file from the explorer in the left side of the panel.
8. On your local machine, run the following hashcat command with the recovered potfile to match real usernames with cracked password `hashcat --potfile-path hashcat.potfile --hash-type 1000 --username example.ntds wordlists/rockyou.txt`

:warning: For every 12hrs or so Disk, RAM, VRAM, CPU cache etc data that is on our alloted virtual machine will get **erased**. 

:information_source: Markvov chain are enabled in default hashcat version. P100 GPU is an equivalent of GTX1080.


## Hashcat Cheatsheet

Here are some of the most used attack modes for the `--attack-mode` option
```
0     Wordlist (with or without rules)
3     Pure bruteforce
```

Here are some of the most used hash types for the `--hash-type` option

```ps1
1000     NTLM (actually its for NT hashes)
3000     LM
5500     Net-NTLMv1 (actually, it should be called NTLMv1)
5600     Net-NTLMv2 (actually, it should be called NTLMv2)
13100    Kerberoast
18200    ASREProast
22000    WPA-PBKDF2-PMKID+EAPOL
16800    WPA-PMKID-PBKDF2
0        md5
100      sha1
1400     sha2-256
1700     sha2-512
```

Hashcat masks for custom cracking

```powershell
command: -a 3 ?l?l?l?l?l?l?l?l
keyspace: aaaaaaaa - zzzzzzzz

command: -a 3 -1 ?l?d ?1?1?1?1?1
keyspace: aaaaa - 99999

command: -a 3 password?d
keyspace: password0 - password9

command: -a 3 -1 ?l?u ?1?l?l?l?l?l19?d?d
keyspace: aaaaaa1900 - Zzzzzz1999

command: -a 3 -1 ?dabcdef -2 ?l?u ?1?1?2?2?2?2?2
keyspace: 00aaaaa - ffZZZZZ

command: -a 3 -1 efghijklmnop ?1?1?1
keyspace: eee - ppp
```

## References & Ideas

* https://github.com/mxrch/penglab
* https://github.com/ShutdownRepo/hashonymize
* https://github.com/ShutdownRepo/google-colab-hashcat
* https://github.com/carlmon/Hashcat-Azure
* https://durdle.com/2017/04/23/using-hashcat-to-crack-hashes-on-azure/
* https://www.trillsecurity.com/tutorials/automating-hashtopolis-with-terraform-part-i/
* https://www.trillsecurity.com/tutorials/automating-hashtopolis-with-terraform-part-ii/
