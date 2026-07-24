# File Reading Commands, Echo aur Redirection

## 1. File ko Read Karna

Linux/Unix terminal mein file ka content read karne ke kai tareeqe hain, jo file ke size aur zaroorat ke hisaab se use hote hain.

### `cat` Command

**`cat`** command file ka poora text seedha terminal par **ek saath (full form mein)** show kar deti hai.

Agar file bohot bari ho jaise agar file mein **1000 lines** ka text ho to `cat` command se pura content ek saath screen par aa jayega, jise parhna mushkil ho jata hai kyunke content scroll ho kar upar chala jata hai aur shuru ka hissa nazar nahi aata.

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

**`head`** command file ke **shuru ke tarikban 10 lines** show karti hai (default).

AAgar hum chahy to 50 lines m sy 25 lines show krwa sakty hain, jaise:

`head -n 25 filename`

Ye command file ki **shuru ki 25 lines** show karegi.

### `tail` Command

**`tail`** command file ke **last (bottom) 10 lines** show karti hai (default), jo file ke **ending/latest data** dekhne ke liye useful hai.

Basic syntax:

`tail filename`

Agar aap specific tadad mein lines dekhna chahte hain, to:

`tail -n 25 filename`

Ye command file ki **aakhri 25 lines** show karegi.

### `tail -f` Command

**`tail -f`** command file ko **"live running form"** mein show karti hai matlab agar file mein naya data continuously add ho raha ho, to ye command us naye data ko **real-time mein** automatically show karti rehti hai, bina baar baar command dobara chalaye.

**Example:**

Agar aap ek terminal mein `tail -f filename` chala kar file ko live monitor kar rahe hain, aur usi waqt **doosre (second) terminal** mein ye command run karein:

`echo "try, etc, attacker hack file" >> filename`

To jo bhi naya data doosre terminal se us file mein add (append) hoga, wo **turant pehle (1st) terminal mein automatically show ho jayega**, kyunke `tail -f` file ko live watch kar rahi hoti hai.

## 2. `echo` Command

**`echo`** ka basic matlab hai "sound" ya "awaz ka izhaar karna" is command ka kaam hota hai **terminal par text ko print/display** karna.

**Example 1:**

`echo "Kali Linux"`

Output: `Kali Linux`

**Example 2:**

`echo "Hello"`

Output: `Hello`

## 3. Redirection Operators — `>` aur `>>` 

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

## 4. Wildcards — `*`, `?` aur `[ ]` (Range)

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