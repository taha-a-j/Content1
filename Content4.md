# Operating System, Kernel, Process, Thread aur CLI Commands

## 1. Operating System (OS) kya hai?

**OS** ek **middle-man** hoti hai user aur computer hardware ky between. Jab bhi user koi task run karna chahta hai, uski request pehle OS ke paas jati hai, aur OS decide karta hai ke us task ko kaise complete karna hai.

- Har task jo computer par execute hota hai, wo actually **Kernel ke through** hi hota hai.
- Bohot saari operating systems **kernel ke upar** banti hain jaise **Windows, macOS, Ubuntu, Kali Linux** etc. Ye sab andar se kernel ke functions use karti hain, lekin apna alag user interface aur features provide karti hain.  

## 2. Kernel kya hai?

**Kernel** OS ka **core part** hota hai jo directly hardware se communicate karta hai. Ye OS se requests leta hai aur decide karta hai ke computer ke resources (CPU, RAM, ROM) ko kaise use karna hai task complete karne ke liye.

**Communication ka basic flow:**

        [Kernel → CPU → RAM → ROM]

Kernel CPU ko instructions bhejta hai, CPU RAM (temporary memory) use kar ke data process karta hai, aur zaroorat parhne par ROM (permanent memory) bhi access kar sakta hai.

## 3. Process kya hai?

**Process** ek program hota hai jo currently run/execute ho raha hota hai.

- Har process banate waqt usko ek **unique Process ID (PID)** milti hai.
- Ek process ke andar **multiple threads** ho sakte hain.
- Har thread ki bhi apni **alag unique ID** hoti hai, jo process ki ID se different hoti hai.
- Alag-alag processes OS **independently distribute aur manage** karta hai, aur ek process ke andar jo threads hain unko us process ke andar hi manage kiya jata hai.

## 4. Thread kya hai?

**Thread** process ke andar execution ki **sabse chhoti unit** hoti hai matlab ek single task ya instruction sequence jo process ke andar chal raha hota hai.
  
### Example:
Process ko aap ek **human body** samjhein, aur threads ko us body ke **internal parts/organs** jo body ke andar kaam kar rahe hain. Jaise organs milkar body ko chalate hain, waise hi threads milkar ek process ko chalate hain.

### Process aur Thread ke important points:

- Ek **active process** mein hamesha **kam se kam ek active thread** zaroor hota hai.
- Ek single process **multiple threads ek saath** run kar sakta hai — isko **multithreading** kehte hain. Ye threads task ke different sections/parts par ek hi waqt mein kaam karte hain.
- Agar **ek thread kharab (crash) ho jaye**, to iska asar **doosre threads par bhi** parh sakta hai, aur poore process ko bhi affect kar sakta hai.
- Jab aap koi **application** run karte hain, to wo ek **process** start karta hai. Wo process apna kaam efficiently complete karne ke liye **multiple threads** create aur use karta hai.

## 5. Operating System — CLI (Command Line Interface)

CLI ek text-based tareeqa hai jahan user commands type karke computer ko instructions deta hai, GUI (buttons/icons) use karne ke bajaye.

## Basic Navigation Commands

- **pwd** (Print Working Directory) — Batata hai ke aap is waqt kis folder mein maujood hain, poora path show karta hai.

- **ls** — Current directory ke andar maujood tamam files aur folders ki list dikhata hai.

- **cd** (Change Directory) — Ek folder se doosre folder mein move karne ke liye use hota hai.
  - `cd foldername` → us folder ke andar jane ke liye (`cd Downloads`, `cd Desktop`)
  - `cd ..` → ek step peeche, parent directory (upar wale folder) mein jane ke liye
  - `cd` (akela) → seedha home directory mein wapis le aata hai
  - `cd /` → system ke root directory mein le jata hai (Linux/Unix ka sabse top-level folder)
  - `cd Desktop/Day1` → ek hi baar mein nested folder (sub-folder ke andar sub-folder) mein jane ke liye

## File Management Commands

- **touch filename** — Ek nayi khaali (empty) file banane ke liye. Jaise: `touch file.txt` se "file.txt" naam ki nayi file ban jayegi.
- **cat filename** (concatenate) — File ka content seedha terminal par dikhane ke liye. Jaise: `cat file.txt` se us file ka content screen par show hoga.
- **rm filename** (remove) — File ya folder delete karne ke liye use hota hai.
  - `rm file.txt` → single file delete
  - `rm -r foldername` → poora folder delete (recursive)

## Other Useful Commands

- **clear** — Terminal screen saaf kar deta hai, purani commands aur output hata kar screen fresh dikhata hai.
- **date** — System ki current date aur time dikhata hai.

## Extra Concept

- **/root** — Ye "root user" (system administrator / superuser) ka home directory hota hai, jo normal user ke home folder se alag hota hai — sirf admin access ke liye reserved.

## 6. Summary

- **OS** user aur hardware ke darmiyan middle-man ka kaam karta hai.
- **Kernel** OS ka core part hai jo directly hardware ko control karta hai.
- **Process** ek running program hota hai jiski apni unique ID hoti hai.
- **Thread** process ke andar execution ki sabse chhoti unit hai, aur ek process mein multiple threads ho sakte hain (multithreading).
- **CLI commands** terminal ke through computer ko directly instructions dene 
ka fast tareeqa hain, jo navigation, file management, aur system information ke liye zaroori hain.