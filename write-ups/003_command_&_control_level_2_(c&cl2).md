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



## ⚠️ Difficulties



### 📚 Lessons Learned


