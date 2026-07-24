# File Type Detection, Hidden Files aur Session Key

## 1. File Type Pata Karna `file` Command

Linux/Unix mein **`file`** command use hoti hai ye pata karne ke liye ke koi file **asal mein kis type ki hai** yani uska real format kya hai, chahe uski extension kuch bhi likhi ho. Ye command file ke andar maujood content ko analyze kar ke uski **exact type, encoding aur details** batati hai.

**Basic syntax:**

`file filename`

### Example 1 — `my.txt`

`file my.txt`
Iska output kuch is tarah hoga:
`my.txt: Unicode text, UTF-8 text, with very long lines (1074)`

Iska matlab hai ke ye file ek **text file** hai jo **Unicode format** mein hai, aur uska **encoding UTF-8** hai (jo internationally standard text encoding hai, jismein English ke ilawa doosri languages ke characters bhi properly show hote hain). "With very long lines (1074)" ka matlab hai ke file mein kam se kam ek line aisi hai jiski length **1074 characters** tak jati hai.

### Example 2 — `my.pdf`

`file my.pdf`
Iska output kuch is tarah hoga:
`my.pdf: PDF document, version 1.5`

Iska matlab hai ke ye file ek **asal PDF document** hai, aur uska **PDF version 1.5** hai. Ye command confirm kar deti hai ke file sach mein PDF hai, sirf naam mein ".pdf" likhne se nahi.

### Example 3 — `file1.jpg`

`file file1.jpg`
Agar file waqai ek image ho, to iska output kuch is tarah hoga:
`file1.jpg: JPEG image data`

Ye batata hai ke file ek **JPEG image** hai. Agar koi file sirf naam mein ".jpg" likh kar kisi doosri type ki file ko chupane ki koshish kare, to `file` command se uski **asli type** pakri ja sakti hai, jo security ke lihaz se bohot important hoti hai.

### `file` Command Kyun Zaroori Hai

- Kabhi kabhi files ki **extension galat ya jaan bujh kar change** kar di jati hai (jaise koi executable file ".txt" ka naam de kar chupa di jaye). `file` command asal content check kar ke **sahi type** batati hai.
- Ye cybersecurity mein bhi useful hai, jahan suspicious files ki asli nature pata karni hoti hai bina unhe open kiye.

## 2. Hidden Files

**Hidden files** wo files hoti hain jo normal `ls` command se **nazar nahi aatin**, aur inhe dekhne ke liye special command use karni parti hai.

Linux/Unix systems mein hidden files ke naam ke **shuru mein dot (`.`) laga hota hai**, jaise `.bashrc` ya `.config`. Dot se shuru hone wali har file ya folder system automatically hidden treat karta hai.

### Hidden Files Command

**`ls -a`**

Ye command current directory ke andar **sari files aur folders dikhati hai, hidden files included**. Normal `ls` command sirf visible files dikhati hai, lekin `ls -a` use karne se system un files ko bhi show kar deta hai jo dot se shuru hoti hain.

Jab `ls -a` run karte hain, to output mein aksar do special entries bhi dikhti hain:

- **`.`** — Ye current directory (jis folder mein aap abhi maujood hain) ko represent karta hai.
- **`..`** — Ye parent directory (ek step upar wale folder) ko represent karta hai.

Ye dono entries har directory mein automatically maujood hoti hain, aur inka use navigation ke liye hota hai (jaise `cd ..` command isi `..` reference ko use karti hai upar wale folder mein jane ke liye).

## 3. Session Key (Instagram Example)

**Session Key** ek unique aur temporary code/token hota hai jo kisi bhi online account (jaise Instagram) mein login karne ke baad **user ki current session ko identify** karne ke liye use hota hai.

Jab koi user apni **Instagram ID mein login karta hai**, to server us user ko ek **session key (ya session token)** assign kar deta hai. Ye session key us waqt tak valid rehta hai jab tak user **logged in** hai, aur ye system ko batata hai ke ye request **usi authenticated user** ki taraf se aa rahi hai, bina baar baar password dobara maangne ke.

### Session Key Kaam Kaise Karta Hai

- Jab user login karta hai (username aur password ke through), server login verify karta hai aur ek **unique session key generate** kar ke user ke device (browser ya app) ko bhej deta hai.
- Iske baad, jab bhi user koi action perform karta hai (jaise post like karna, scroll karna, message bhejna), to app har request ke saath ye **session key bhi server ko bhejta hai**, taake server confirm kar sake ke ye request **valid aur logged-in user** ki hai.
- Jab tak session key valid hai, user ko baar baar login karne ki zaroorat nahi parti.
- Agar user **logout** kar de, ya session key **expire** ho jaye, to purani session key **invalid** ho jati hai, aur user ko dobara login karna parta hai.

### Session Key importance (Security Perspective)

Session key ek **sensitive/private data** hoti hai, kyunke agar ye kisi doosre insaan ke haath lag jaye, to wo bina password jaane bhi **us user ke account ko access** kar sakta hai is process ko **"session hijacking"** kehte hain. Isi wajah se session keys ko protect karna aur inhe safely store karna security ke accroding se bohot zaroori hota hai.

## Summary

- **`file`** command kisi bhi file ki **asal type** pata karne ke liye use hoti hai, sirf uski extension par bharosa karne ke bajaye — jaise text files, PDF documents, ya image files ko unke asal content ke zariye identify karna.
- **Hidden files** wo files hoti hain jinke naam **dot (`.`) se shuru** hote hain, aur ye normal `ls` se nazar nahi aatin. Inhe dekhne ke liye **`ls -a`** command use hoti hai, jo `.` (current directory) aur `..` (parent directory) bhi show karti hai.
- **Session Key** ek unique temporary token hai jo login ke baad server aur user ke darmiyan **identity verify** karne ke liye use hota hai (jaise Instagram login ke baad), aur ye account security ke liye ek sensitive cheez hoti hai jise protect karna zaroori hota hai.