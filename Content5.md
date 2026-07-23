# Root Level, User Level, Logs aur Practical CLI Commands

## 1. Root Level aur User Level
**Root Level** aur **User Level** do alag tarah ki access permissions hoti hain kisi bhi Linux/Unix based system mein.

**Root Level** system ka sabse basic aur sabse powerful level hai ye **pure system par full access** deta hai. Root level par wo tamam kaam kiye ja sakte hain jo ek **normal user perform nahi kar sakta**, jaise system files change karna, naye users banana, permissions set karna, ya system-level settings modify karna.

**User Level** ek normal user ki access hoti hai, jismein limited permissions hoti hain taake system secure rahe aur koi aam user galti se important system files ko access na kry. 

### User se Root Level tak Request Kaise Jati Hai

Jab ek normal user ko root level ki access chahiye hoti hai, to wo apni request **"sudo"** command ke through bhejta hai. Yani normal user "sudo" command use kar ke temporarily root-level permissions le leta hai kisi specific command ko run karne ke liye.

### Commands (Root/User Level)

`sudo`: Agar aap **root login nahi hain** (yani normal user hain) aur koi command root/administrator permissions ke saath run karna chahte hain, to command se pehle `sudo` likhte hain. Jaise: `sudo apt update`.

`sudo -i`: Agar aap **directly root user ke tor par login** hona chahte hain (na ke sirf ek command ke liye), to ye command use hoti hai. Ye aapko poori root shell mein le jati hai jahan aap bina baar baar "sudo" likhe root-level commands run kar sakte hain.

`exit`: Jab aap root login se wapis **normal user par aana** chahein, to ye command use hoti hai.

## 2. Logs kya hote hain?

**Logs** wo **data hote hain jo kabhi khatam (delete) nahi hote**, chahe user unhe manually delete karne ki koshish kare.

### Logs Kaise Kaam Karte Hain

Jab aap apni files ya messages **delete** karte hain jaise agar aapke paas USB (external storage) hai aur aap us mein se data delete karte hain to wo data dikhne mein delete ho jata hai, lekin uske **logs delete nahi hote**.

Ye logs **encrypted form mein save** hote hain, matlab wo ek coded/locked shakal mein store hote hain jo normal tareeqe se parhe nahi ja sakte. Agar zaroorat pare to inhe **decrypt** kiya ja sakta hai, aur decrypt karne ke baad wo data dobara wapis (recover) kiya ja sakta hai.

Ye logs system mein **"var" (variable data)** ke naam ki location/folder mein save hote hain.

### Example: Logs Kis Tarah Bante Hain

Agar aap apne **mobile phone par koi bhi activity/action perform karte hain** jaise mobile ko open karna, unlock karna, ya kisi bhi folder ko access karna to ye har action kisi na kisi folder mein automatically **save ho jata hai**, aur yahi cheez **"logs"** kehlati hai.

Yani simple lafzon mein: **har activity ka ek record system automatically bana leta hai**, chahe user ne wo data delete bhi kar diya ho asal record (log) phir bhi kahin na kahin save reh jata hai.

## 3. CLI Commands: File && Folder, Manage Karna

`cd` folder ke andar jana mein jany k liya jahan hum apna kaam karenge.

`mkdir Task` new folder bana.

`cd Task` us naye banaye gaye "Task" folder ke andar le jati hai.

`ls` file,folder list.

`touch Task.txt` "Task.txt, Notes.txt,Bachup.txt etc" naam ki ek nayi khaali file banati hai.

`ls` Dobara list check krna taake pata chale ke "Task.txt" file ban chuki hai ya nai.

`cat Task.txt` file ka content terminal par dikhati hai. text ki form mai. `nano Task.txt` file ko **edit karne ke liye** kholti hai.
Nano ek text editor hai jo terminal ke andar hi file mein likhne ki access deta hai.
File mein likhne ke baad, save aur close karne ka tareeqa: `Ctrl + X` ,`Y`+`Enter`.

`cat Task.txt` File content dekhny k liya.

`ls -R` List dekhna 

`cp` **(Copy)** kisi file ya folder ko **copy** karne ke liye use hoti hai.

`mv` **(Move)** kisi file ya folder ko **ek jagah se doosri jagah move** karne ke liye use hoti hai. Ye file ka **naam change (rename)** karne ke liye bhi use hoti hai.

`rm` **file ko delete** karne ke liye.

`rm -r` **poora folder delete krny k liya** 
rm -r se delete hui files trash/recycle bin mein nahi jaatin seedha permanently delete ho jaati hain. Isliye pehle **ls -la** se check kar lein chahiyan then `rm -r`.

`rmdir` **khaali folder ko delete** karne ke liye.

## Summary

- **Root level** system ki full/highest access hoti hai, jabke **user level** limited access hoti hai.
- Normal user `sudo` command se temporarily root access le sakta hai, aur `sudo -i` se poori tarah root user ban sakta hai. Wapis normal user par jane ke liye `exit` use hota hai.

- **Logs** wo records hote hain jo har activity (chahe file delete hi kyun na ho) ko save kar lete hain, aur ye encrypted form mein "var" location mein store hote hain inhe delete karna mumkin nahi hota, sirf decrypt kar ke wapis dekha ja sakta hai.

