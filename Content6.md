# Root Level, User Level, Logs, CLI Commands, File Reading, Echo aur Wildcards

## 1. Root Level aur User Level

**Root Level** aur **User Level** do alag tarah ki access permissions hoti hain kisi bhi Linux/Unix based system mein.

**Root Level** system ka sabse basic aur sabse powerful level hai — ye **pure system par full access** deta hai. Root level par wo tamam kaam kiye ja sakte hain jo ek **normal user perform nahi kar sakta**, jaise system files change karna, naye users banana, permissions set karna, ya system-level settings modify karna.

**User Level** ek normal user ki access hoti hai, jismein limited permissions hoti hain taake system secure rahe aur koi aam user galti se important system files ko access na kare.

### User se Root Level tak Request Kaise Jati Hai

Jab ek normal user ko root level ki access chahiye hoti hai, to wo apni request **"sudo"** command ke through bhejta hai. Yani normal user "sudo" command use kar ke temporarily root-level permissions le leta hai kisi specific command ko run karne ke liye.

### Commands (Root/User Level)

`sudo` — Agar aap **root login nahi hain** (yani normal user hain) aur koi command root/administrator permissions ke saath run karna chahte hain, to command se pehle `sudo` likhte hain. Jaise: `sudo apt update`.

`sudo -i` — Agar aap **directly root user ke tor par login** hona chahte hain (na ke sirf ek command ke liye), to ye command use hoti hai. Ye aapko poori root shell mein le jati hai jahan aap bina baar baar "sudo" likhe root-level commands run kar sakte hain.

`exit` — Jab aap root login se wapis **normal user par aana** chahein, to ye command use hoti hai.

---

## 2. Logs kya hote hain?

**Logs** wo **data hote hain jo kabhi khatam (delete) nahi hote**, chahe user unhe manually delete karne ki koshish kare.

### Logs Kaise Kaam Karte Hain

Jab aap apni files ya messages **delete** karte hain — jaise agar aapke paas USB (external storage) hai aur aap us mein se data delete karte hain — to wo data dikhne mein delete ho jata hai, lekin uske **logs delete nahi hote**.

Ye logs **encrypted form mein save** hote hain, matlab wo ek coded/locked shakal mein store hote hain jo normal tareeqe se parhe nahi ja sakte. Agar zaroorat pare to inhe **decrypt** kiya ja sakta hai, aur decrypt karne ke baad wo data dobara wapis (recover) kiya ja sakta hai.

Ye logs system mein **"var" (variable data)** ke naam ki location/folder mein save hote hain.

### Example: Logs Kis Tarah Bante Hain

Agar aap apne **mobile phone par koi bhi activity/action perform karte hain** — jaise mobile ko open karna, unlock karna, ya kisi bhi folder ko access karna — to ye har action kisi na kisi folder mein automatically **save ho jata hai**, aur yahi cheez **"logs"** kehlati hai.

Yani simple lafzon mein: **har activity ka ek record system automatically bana leta hai**, chahe user ne wo data delete bhi kar diya ho — asal record (log) phir bhi kahin na kahin save reh jata hai.

## 3. CLI Commands — File aur Folder Manage Karna

`cd` — Folder ke andar jane ke liye use hota hai, jahan hum apna kaam karenge.

`mkdir Task` — Naya folder banata hai.

`cd Task` — Us naye banaye gaye "Task" folder ke andar le jati hai.

`ls` — File aur folder ki list dikhati hai.

`touch Task.txt` — "Task.txt", "Notes.txt", "Backup.txt" waghera naam ki ek nayi khaali file banati hai.

`ls` — Dobara list check karne ke liye, taake pata chale ke "Task.txt" file ban chuki hai ya nahi.

`cat Task.txt` — File ka content terminal par text ki form mein dikhati hai.

`nano Task.txt` — File ko **edit karne ke liye** kholti hai. Nano ek text editor hai jo terminal ke andar hi file mein likhne ki access deta hai. File mein likhne ke baad, save aur close karne ka tareeqa: `Ctrl + X`, phir `Y`, phir `Enter`.

`cat Task.txt` — File ka content dobara dekhne ke liye.

`ls -R` — Folder aur uske andar maujood sub-folders ki poori list (recursively) dikhane ke liye.

`cp` (Copy) — Kisi file ya folder ko **copy** karne ke liye use hoti hai.

`mv` (Move) — Kisi file ya folder ko **ek jagah se doosri jagah move** karne ke liye use hoti hai. Ye file ka **naam change (rename)** karne ke liye bhi use hoti hai.

`rm` — **File ko delete** karne ke liye use hoti hai.

`rm -r` — **Poora folder delete** karne ke liye use hoti hai. `rm -r` se delete hui files trash/recycle bin mein nahi jaatin, seedha permanently delete ho jaati hain. Isliye pehle `ls -la` se check kar lena chahiye, phir `rm -r` use karna chahiye.

`rmdir` — **Khaali folder ko delete** karne ke liye use hoti hai.

## 4. File ko Read Karna

### `cat` Command

**`cat`** command file ka poora text seedha terminal par **ek saath (full form mein)** show kar deti hai. Agar file bohot bari ho — jaise agar file mein **1000 lines** ka text ho — to `cat` command se pura content ek saath screen par aa jayega, jise parhna mushkil ho jata hai kyunke content scroll ho kar upar chala jata hai aur shuru ka hissa nazar nahi aata.

### `less` Command

**`less`** command file ko **"book" ki tarah page by page** show karti hai, jisse badi files ko aasani se parha ja sakta hai. `less` ke andar kuch useful shortcuts hain:

- **`/`** — File ke andar **koi specific word search** karne ke liye use hota hai.
- **`q`** — File se **bahar nikalne (quit karne)** ke liye use hota hai.
- **`b`** — Ek page **peeche (back)** jane ke liye use hota hai.
- **`G`** — File ke **sabse last (end)** tak seedha jane ke liye use hota hai.
- **`g`** — File ke **sabse upar (start)** tak seedha jane ke liye use hota hai.
- **Arrow keys (`↑`, `↓`)** — Line by line **upar ya neeche** move karne ke liye use hote hain.
- **`Space`** — Ek **poora page neeche** jane ke liye use hota hai.

### `head` Command

**`head`** command file ke **shuru ke tarikban 10 lines** show karti hai (default). Agar aap chahen to lines ki tadad khud specify kar sakte hain:

`head -n 25 filename`

Ye command file ki **shuru ki 25 lines** show karegi.

### `tail` Command

**`tail`** command file ke **aakhri (bottom) 10 lines** show karti hai (default), jo file ke **ending/latest data** dekhne ke liye useful hai.

Basic syntax:

`tail filename`

Agar aap specific tadad mein lines dekhna chahte hain, to:

`tail -n 25 filename`

Ye command file ki **aakhri 25 lines** show karegi.

### `tail -f` Command

**`tail -f`** command file ko **"live running form"** mein show karti hai — matlab agar file mein naya data continuously add ho raha ho, to ye command us naye data ko **real-time mein** automatically show karti rehti hai, bina baar baar command dobara chalaye.

**Practical Example:**

Agar aap ek terminal mein `tail -f filename` chala kar file ko live monitor kar rahe hain, aur usi waqt **doosre (second) terminal** mein ye command run karein:

`echo "try, etc, attack" >> filename`

To jo bhi naya data doosre terminal se us file mein add (append) hoga, wo **turant pehle (1st) terminal mein automatically show ho jayega**, kyunke `tail -f` file ko live watch kar rahi hoti hai.

## 5. `echo` Command

**`echo`** ka basic matlab hai "sound" ya "awaz ka izhaar karna" — is command ka kaam hota hai **terminal par text ko print/display** karna.

**Example 1:**

`echo "Kali Linux"`

Output: `Kali Linux`

**Example 2:**

`echo "Hello"`

Output: `Hello`

## 6. Redirection Operators — `>` aur `>>`

Redirection operators terminal ke output ko **file ke andar bhejne (redirect karne)** ke liye use hote hain, taake output screen par dikhne ke bajaye file mein save ho jaye.

### Single Arrow `>` (Overwrite / Replace)

**`>`** operator jo bhi naya data likha jata hai, wo file ke **purane content ko replace (overwrite)** kar deta hai — matlab purana data mit jata hai aur sirf naya data file mein reh jata hai.

**Example:**

`echo "Kali linux" > filename`

Is command se file ke andar sirf **"Kali linux"** likha hua save hoga, aur agar file mein pehle se koi aur data tha to wo **replace ho jayega**.

**Folder/File Banane ka Practical Example:**

`echo "Ali" > football.txt`

Is command se "football.txt" naam ki file ban jayegi (agar pehle se maujood nahi thi), aur us mein "Ali" likh kar save ho jayega. Iske baad, `ls` command use kar ke check kiya ja sakta hai ke file successfully ban chuki hai ya nahi.

### Double Arrow `>>` (Append / Add)

**`>>`** operator naya data file ke **purane content ko replace nahi karta**, balke purane content ke **saath add (append)** kar deta hai — is tarah file mein data **line by line jama** hota rehta hai.

**Example:**

`echo "Me" >> filename`

Is command se "Me" naya text file ke **end mein add ho jayega**, purana content jaisa tha waisa hi mehfooz rahega.

## 7. Wildcards — `*`, `?` aur `[ ]` (Range)

Wildcards special symbols hote hain jo terminal mein **multiple files ko ek saath match/search** karne ke liye use hote hain, taake har file ka naam alag se type na karna pare.

### `*` (Star) — Sab Kuch Match Karta Hai

**`*`** wildcard ka matlab hai **"sari files jo ek jaisi type ki hon"** — ye kisi bhi tadad ke characters ki jagah use ho sakta hai.

**Example:**

`ls *.pdf`

Ye command current folder ke andar maujood **tamam PDF files** ko ek saath list kar degi, chahe unke naam kuch bhi hon.

`*` sirf `ls` ke saath nahi, balke doosre commands ke saath bhi use hota hai:

`cp *.txt` — Is folder ki **tamam `.txt` files ko copy** karne ke liye use hoti hai.

`rm *.txt` — Is folder ki **tamam `.txt` files ko delete** karne ke liye use hoti hai.

`mv *.txt` — Is folder ki **tamam `.txt` files ko move ya rename** karne ke liye use hoti hai.

### `?` (Question Mark) — Single Alphabet/Character Match Karta Hai

**`?`** wildcard **sirf ek single character (alphabet ya digit)** ki jagah use hota hai — matlab ye `*` ki tarah "sab kuch" nahi, balke **sirf ek position** ko represent karta hai.

**Example:**

`ls ?.txt`

Ye command sirf un files ko dikhayegi jinke naam mein **sirf ek character ho** (jaise `a.txt`, `1.txt`), lekin `abc.txt` jaisi files is mein show nahi hongi kyunke uska naam ek se zyada characters ka hai.

`ls file?.txt`

Ye command un files ko match karegi jinke naam "file" ke baad **sirf ek extra character** ho, jaise `file1.txt`, `file2.txt`, `fileA.txt` waghera.

### `[ ]` (Square Brackets) — Range ya Choice Match Karta Hai

**`[ ]`** wildcard use hota hai jab hum kisi **specific range ya choices** mein se koi ek character match karna chahte hain.

Agar naam mein numbers likhe hon, to ye range ke digits ko represent karta hai. Jaise agar files ke naam `file1`, `file2`, `file3` waghera hon, to `[ ]` in specific numbers ko target karne ke liye use hota hai.

**Important Point:** `[10]` ka matlab **"10" number nahi hota**, balke iska matlab hota hai ke **"1" ya "0"** — yani `[ ]` ke andar diye gaye har digit ko **ek alag choice** samjha jata hai, poora number nahi.

**Example 1:**

`ls file[10].txt`

Ye command sirf `file1.txt` ya `file0.txt` ko match karegi — **`file10.txt` ko match nahi karegi**, kyunke `[10]` iska matlab "1 ya 0" hai, "10" nahi.

**Example 2 — Range ke saath:**

`ls file[1-3].txt`

Ye command un files ko match karegi jinke naam mein "file" ke baad **1 se 3 tak koi bhi ek digit** ho — yani ye `file1.txt`, `file2.txt`, aur `file3.txt` teeno ko match kar degi, kyunke `[1-3]` ek **range** define karta hai.

## Summary

- **Root level** system ki full/highest access hoti hai, jabke **user level** limited access hoti hai. Normal user `sudo` command se temporarily root access le sakta hai, aur `sudo -i` se poori tarah root user ban sakta hai. Wapis normal user par jane ke liye `exit` use hota hai.
- **Logs** wo records hote hain jo har activity (chahe file delete hi kyun na ho) ko save kar lete hain, aur ye encrypted form mein "var" location mein store hote hain — inhe delete karna mumkin nahi hota, sirf decrypt kar ke wapis dekha ja sakta hai.
- File aur folder banane, edit karne, copy/move karne aur delete karne ke liye commands hain: `mkdir`, `cd`, `ls`, `ls -R`, `touch`, `cat`, `nano`, `cp`, `mv`, `rm`, `rm -r`, aur `rmdir`.
- File parhne ke liye **`cat`** (poora content ek saath).
- **`less`** (page by page), **`head`** (shuru ki lines)
- **`tail`** (aakhri lines) commands use hoti hain.
- **`tail -f`** file ko **live/real-time** monitor karne ke liye use hoti hai.
- **`echo`** command terminal par text print/display karne ke liye use hoti hai.
- **`>`** operator file ke purane content ko **replace (overwrite)** karta hai.
- **`>>`** operator naye data ko purane content ke **saath add (append)** karta hai.
- **`*`** wildcard kisi bhi tadad ke characters match karta hai.
- **`?`** sirf ek single character match karta hai.
- **`[ ]`** specific digits/characters ka range ya choice define karta hai.