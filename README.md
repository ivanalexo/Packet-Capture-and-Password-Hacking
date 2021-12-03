# Packet-Capture-and-Password-Hacking
* First dowload [Krb 816 zip file](https://wiki.wireshark.org/SampleCaptures?action=AttachFile&do=get&target=krb-816.zip)
* Then open it with some sniffing tool like Wireshark or NetworkMiner
For this I'm using NetworkMiner
## Cracking user 1
![imagen](https://user-images.githubusercontent.com/29745174/144626444-8c55d1dc-2737-4627-ba47-dd33d2e1b2db.png)

Going to **Credentials** tab
![imagen](https://user-images.githubusercontent.com/29745174/144626971-bc382663-3bfc-40ed-9e98-d06ec4822b33.png)

First select **des** user and copy the password

![imagen](https://user-images.githubusercontent.com/29745174/144627298-4dc4950f-c95e-4f6e-b92f-992c930cf0e4.png)

Using **Hashcat tool** to apply a brute force attack to kerberos hashes I used this command `hashcat -a 3 -m 7500 --status -o cracked1.txt user1.txt` replace **user1.txt** for the name of your hash file.
![imagen](https://user-images.githubusercontent.com/29745174/144628652-6880ff35-772f-4684-b661-7f696c04615d.png)

After a short while, the hash is cracked

![imagen](https://user-images.githubusercontent.com/29745174/144628798-dd2e91cc-5360-4f85-a764-ed793e74a2ae.png)

And the password for **des** user is **123**

## Cracking user 2
We do the same process for extrecting **u5** user passwrod

![imagen](https://user-images.githubusercontent.com/29745174/144629459-708ff11a-8f53-49fb-af72-a44430c29f4e.png)

In this case I'm gonna use **john the ripper** `john --format=krb5pa-md5 -w=/usr/share/wordlist/rockyou.txt user2.txt`

![imagen](https://user-images.githubusercontent.com/29745174/144630541-92692e7b-4e04-48c1-982d-c5efdfa5b4af.png)

And as we can see the password is **123** as well.
