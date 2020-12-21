# Nephelees
Néphélées (Νεφήλαι, Nephḗlai) : cloud nymphs greek - also ntds cracking tool abusing Google Colab 

<p align="center">
  <a href="https://colab.research.google.com/github/swisskyrepo/Nephelees/blob/main/google_colab_hashcat.ipynb" target="_parent"><img src="https://colab.research.google.com/assets/colab-badge.svg" alt="Open In Colab"/></a>
</p>

## V1 - Google Colab

* https://github.com/ShutdownRepo/hashonymize
* https://github.com/ShutdownRepo/google-colab-hashcat
* https://github.com/mxrch/penglab
* https://colab.research.google.com/drive/1arm1_HEMb868mk18FlLkEcqvHPB_Ibgb#scrollTo=lWPQqb3oETLd

```ps1
Go on : https://colab.research.google.com/github/mxrch/penglab/blob/master/penglab.ipynb
Select "Runtime", "Change runtime type", and set "Hardware accelerator" to GPU.
Change the config by setting "True" at tools you want to install.
Select "Runtime" and "Run all" !
```

* markov, keyboard walking, dico + rules , haveibeenpwn
* reuse old pot (extract passwd to new wordlist) 

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

# 2 hours
-a 3 -1 ?l?d?u ?1?1?1?1?1?1?1?1
```

## V2 - UI

* https://github.com/Coalfire-Research/npk
* https://github.com/s3inlc/hashtopolis/releases/tag/v0.12.0

## References & Ideas

* https://github.com/carlmon/Hashcat-Azure
* https://durdle.com/2017/04/23/using-hashcat-to-crack-hashes-on-azure/
* https://www.trillsecurity.com/tutorials/automating-hashtopolis-with-terraform-part-i/
* https://www.trillsecurity.com/tutorials/automating-hashtopolis-with-terraform-part-ii/
