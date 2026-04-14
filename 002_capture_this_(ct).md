# [Capture this🔗]([https://www.root-me.org](https://www.root-me.org/en/Challenges/Forensic/Capture-this))

<details>

🔎 Category: Forensic 

🏆 Points: 15

🟡 Level: easy

👤 Author: Zey_Roxx

🗓️ Date: 20/10/2023

✅ Validating: 08/04/2026

</details>

## 🧩 Statement

An employee has lost his `KeePass` password. He couldn’t remember it, and couldn’t find his password file.  
After hours of searching, it turns out that he has sent a screen of his passwords to one of his colleagues,  
but it’s still nowhere to be found.

He’s asking for your help to find him.  
It’s up to you

## 🔍 Initial Analysis

The archive contains a file named `Database.kdbx`, it's can be open with `keePass`,  
and the file `Capture.png`, which look like this:  

![Capture.png](assets/images/003_ct.png)

This screenshot contains 4 passwords.

## 💡 Hypothesis

So I don't see anything suspicious one the screenshot, maybe the flag is just one of the 4 passwords.  
I think I'll just test these 4 

## 🛠️ Exploitation

So we have 4 passwords to test in the keepass or in the answer field, obviously any of them works...,
but I noted that there is a little piece of begining of word on the right edge.
I was realy lost at this moment, I mean how can I recover something cropped ?!?!?

This made me think at somathing, you know sometimes when you crop an image if you open it with the same editor you can see the rest.
So i tested to open it with the `Windows Snipping Tool` and used the crop fonction, but nothing special happened.

I went on the [Root-Me Discord server](https://discord.gg/rootme) and I covered up interesting informations.

![Discord Screenshot](assets/images/004_ct.png)

<details>
  <summary>Voir la traduction</summary>

  Ceci est le texte traduit.

</details>

![Discord Screenshot](assets/images/005_ct.png)

<details>
  <summary>Voir la traduction</summary>

  Ceci est le texte traduit.

</details>

## ⚠️ Difficulties

## 📚 Lessons Learned
