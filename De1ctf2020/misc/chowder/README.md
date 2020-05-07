# Chowder

## Description
>https://drive.google.com/file/d/1-SrQ8JbD8zAQNVlvuwu3T2Lbu_o1knRQ/view?usp=sharing

**Hint**
* The network connection in pcap is not helping to the challenge

* Do not need to connect the network, every data can be extracted from the pcap

* In the burst test point of compressed packet password, the length of the password is 6, and the first two characters are "D" and "E".

## Write-up

# Author

[therealbobo](https://github.com/therealbobo)
[aandryyy](https://github.com/andrea-mengascini)
[Apposto](https://github.com/TheLillo)

# Solution

We imported Misc_Chowder.pcap in Wireshark.
We exported all the images contained in the HTTP Objects.

[One](upload_file(24).php) of them contained this link:

![image](upload_file(24).php)

We downloaded the readme.zip, extracted the readme.docx and found inside **You_found_me_Orz.zip**.

The zip was protectd by password but we knew from the Hint that  the length of the password was 6, with the first 2 characther were "DE". We generated a simple word list and brute forced it.

The password was ```DE34Q1```

Using binwalk we found an hidden file.
From the image we extracted the trailing data.
With 7zip we excracted the 4 file and the flag was in fffffffflllll.txt

```De1CTF{E4Sy_M1sc_By_Jaivy_31b229908cb9bb}```

