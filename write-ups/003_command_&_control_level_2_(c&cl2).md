# [Command & Control - level 2🔗](https://www.root-me.org/en/Challenges/Forensic/Command-Control-level-2)

<details>

🔎 Category: Forensic

🏆 Points: 15

🟡 Level: Easy

👤 Author: Thanat0s

🗓️ Date: 16/02/2013

✅ Validating: 20/04/2026

</details>

## 🧩 Statement

Congratulations Berthier, thanks to your help the computer has been identified.  
You have requested a memory dump but before starting your analysis you wanted to take a look at the antivirus’ logs.  
Unfortunately, you forgot to write down the `workstation’s hostname`.  
But since you have its memory dump you should be able to get it back!

The validation flag is the workstation’s hostname.

## 🔍 Initial Analysis

The archive only contains a file naimed `ch2.dump`, the `.dump` clearly indiquate that the file is under `hexadecimal` format.  
It's quitely adherent with the statement, cause the memoy dump also called the `RAM` dump is also work with `hexadecimal`.

## 💡 Hypothesis

as far as I know, when an `hexadecimal` file contain `string` datas, you can read them with every notepad,  
`nano` might helps me to find the flag and if we are lucky the flag'll be near the head of the dump,  
like it was the case in the CTF [deleted file🔗](https://github.com/MINOTROCK/Root-Me/blob/main/write-ups/001_deleted_file_(df).md) .

## 🛠️ Exploitation

![Firste Step With nano](../assets/images/011_c&cl2.png)

I checked the head of the dump with `nano`, nothing looks liked to a `workstation’s hostname`,  
but now we now what kind of system it was, `Windows`, now it's time for the B plan ! 

The plan is very simple, I'll use `CheatEngine` to take some informations in the `RAM` memory of a `Windows` system.  
Fortunately my computeur is under `Windows`, let me show you what I did with `CheatEngine`,  
but first we have to check my `workstation’s hostname`

![Firste Step With nano](../assets/images/012_c&cl2.png)

This is `msinfo32.exe` thank to it we know that my `workstation’s hostname` is `PC-PORTABLE`,  
let's search this in my `RAM` memory with `CheatEngine`!

![CheatEngine](../assets/images/013_c&cl2.png)

ok just few explanations about my strategie, one program is really iimportant on `Windows`,  
`Program Manager` without this the system doesn't work, it's 100% sure that the dump contains it working datas.  
So I searched my `workstation’s hostname` in the working datas of `Program Manager` and bingo,  
now we know that the `workstation’s hostname` can be find after the mention `USERDOMAIN_ROAMINGPROFILE`.

I just have to search the partial or the entire mention with `grep` in the dump file.

```bash
grep -ab USERDOMAIN ch2.dump
```

![grep](../assets/images/014_c&cl2.png)

Look, the `workstation’s hostname` is here above the 3 on the screenshots.

## ⚠️ Difficulties



### 📚 Lessons Learned


