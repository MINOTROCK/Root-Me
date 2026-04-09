[Deleted File by Manah](https://www.root-me.org/en/Challenges/Forensic/Deleted-file)

[🧩Statement](#)

Your cousin found a USB drive in the library this morning.  
He’s not very good with computers, so he’s hoping you can find the owner of this stick!  
The flag is the owner’s identity in the form "firstname_lastname".  

[🔍 Initial Analysis](#)

After unzipping the archive, you obtain a file named "ch39".  
You can open it with Windows Notepad, but it appears to be slightly corrupted.  
Notepad experiences significant freezing when opening the file.

[💡 Hypothesis](#)

I guess that this file hides the name of the USB drive's owner.  
I didn't find anything else in the archive, and I checked for hidden files.

[🛠️ Exploitation](#)

I examinated the file "ch39" with Notepad and found something that looks like a name.

![Analysis with Notepad](assets/images/001_df.png)

I entered the name in the correct format in the answer field, and it worked.  
Then I checked other solutions and found that there was a hidden image on the USB drive.
So

[⚠️ Difficulties](#)



[📚 Lessons Learned](#)








