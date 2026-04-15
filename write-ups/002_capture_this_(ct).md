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
  <summary>translation</summary>

  *Hello,*
  
  *I’m stuck on this challenge. I found the GitHub repository corresponding to the program that can help process the provided image.*  
  *However, I’m unable to use it. I’ve explored several possibilities—incorrect environment (WSL),*  
  *wrong Python version—but I’m still stuck on what seems to be the final step.*

</details>

![Discord Screenshot](assets/images/005_ct.png)

<details>
  <summary>translation</summary>

  **Itadown**

  *Hello,*  
  *I’m stuck on this challenge—could someone give me a bit of help?*  
  *Thanks in advance.*

  **lYuung**

  *Apparently it’s related to a vulnerability that allows retrieving images from 2023.*  
  *And if you look on the right, there’s the beginning of some code.*  
  *I’m stuck on it as well, though.*

</details>

After some researchs it appear that there existe a vulnerability dated from 2023 can uncrop some images. The name of this is `CVE-2023-21036`,  
well-knowed under the name `Acropalypse`, the vulnerability concern the `Windows Snipping Tool` and the `Google Pixels Snipping Tool`.  
We have to find the `GitHub` but first i will test something with the screenshot with this command:

```bash
grep -abo IEND Capture.png

>162160:IEND
>581412:IEND
```

<details>
  <summary>note</summary>

  when you use `grep` to search somthing in a binary file, you have to use `-a`, here `-bo` is just to facilitate the reading.

</details>

Definitely there is something wrong with this screenshot, the `IEND` is a marquer used to signal the end of a `.png` file.
Normaly ther is only one, I'll try somethning else, I'll remove the unused part to see what happen:

```bash
dd if=003_ct.png of=clean.png bs=1 count=162172
file Clean.png
```

and we got this:

![Clean.png](assets/images/006_ct.png)

Yes it the same image, but this one weidght `160 Ko` the original weidght was `568 Ko`, the diferrence is so hudge !!!
Now let's go find and clone the [Github repository](https://github.com/frankthetank-music/Acropalypse-Multi-Tool).

I tested to start the `Python` program with `WSL Kali-Linux` but it displays an `Error Message` due a "externally-managed-environment".  
I tried to use `Docker` but is not work on `Windows` and `WSL Kali-Linux`, so I used `VMware` but the image selector is broken...  
I also attempted to use the used the `Python` command but one of the two dependencies does not support last `Python` releases.  
My last choice was to use `Pyenv` you can use a `virtuel environement` of `Python`, I configured it to the `3.11.9 version`.
Finaly we got this.

![Acropalypse-Multi-Tool1](assets/images/007_ct.png)
![Acropalypse-Multi-Tool2](assets/images/008_ct.png)

Witch result in this.

![Restored.png](assets/images/009_ct.png)


## ⚠️ Difficulties

## 📚 Lessons Learned
