## CPU & OS Basics

**CPU** = Central Processing Unit
 CPU ek human ki tarah hai, jisko koi task diya jata hai. Ye computer ka "brain" hota hai ye har instruction ko execute (perform) karta hai. Jaise insaan sochta hai aur decision leta hai, waise hi CPU calculations aur instructions ko process karta hai. CPU ke andar bhi chote parts hote hain jaise **ALU** (Arithmetic Logic Unit) (jo calculations/logic karta hai) aur **CU** (Control Unit) (jo instructions ko manage karta hai).  

**OS's Working:**
OS = Operating System. Computer sirf **binary language** (0 aur 1) samajhta hai. Insaan ki normal language (English, Urdu) nahi samajh sakta. Isliye OS ek **translator/middleman** ka kaam karta hai. Ye humari commands (jab hum mouse click karte hain ya app open karte hain) ko binary (zero, one) mein convert karke CPU/hardware tak pohanchata hai, aur wapis result ko humein samajh aane wali form mein screen par dikhata hai.  

Simple words mein: **OS = hardware aur user/software ke beech ka pul (bridge).** Bina OS ke, koi bhi application chalna mushkil hai actually bina OS ke computer bilkul use hi nahi ho sakta, ku ki hardware ko control karne wala koi nahi hoga.
  
**OS (Basic functions):**
- Hardware ko manage karna (CPU, RAM, disk, printer waghera)
- Files aur folders ko organize karna
- Multiple programs ko ek sath chalana (Multitasking)
- Security dena (passwords, permissions)
- User aur hardware ke darmiyan interface dena

**Process:**
CPU level par jo bhi cheezein chal rahi hoti hain, unhe **"Process"** kehte hain. Yani jab koi program **run/execute** ho raha hota hai (memory mein load hoke chal raha hota hai), to us running program ko process kaha jata hai.

Important Note: **Program** wo file hai jo disk mein pari hoti hai (jaise Chrome.exe), aur jab hum usey open karte hain to wo **Process** ban jata hai (yani chalti hui cheez). Ek program se multiple processes bhi ban sakti hain (jaise Chrome ke multiple tabs, har tab ek alag process ki tarah kaam karta hai).

**Doctor Example:**
Doctor check patience one by one means jaise doctor ek time par ek hi patient ko dekhta hai (queue mein), waise hi CPU bhi tasks/processes ko manage karke ek order mein handle karta hai. Isko **CPU Scheduling** kehte hain, OS decide karta hai kis process ko kab aur kitna time ny CPU dena hai, taake sab kaam smoothly aur fairly ho.


## Memory Management

OS decide karta hai ke Chrome vs VS Code ko kitni RAM milegi kyunki RAM limited hoti hai, isliye OS smartly distribute karta hai ke kis app ko kitni zaroorat hai. 

**Application ko space assign karna:** Jab bhi koi app open karte hain, OS us application ko **RAM memory** mein space assign krata hai taake wo chal sake. Jitni RAM zyada hogi, to zyada apps ek sath smoothly chal sakti hain.

Agar wo assigned space **khatam ho jaye** (RAM full ho jaye), to data **store** hone ke liye **SSD ya HDD** ke paas jata hai yani OS temporarily data ko storage disk pe bhej deta hai. Isko **Virtual Memory / Swapping** kehte hain. Ye process RAM se thodi slow hoti hai kyunki disk, RAM se speed mein kaafi peeche hoti hai.  

Agar RAM ka space kam ho (jaise 4GB) aur usmein zyada cheezein jaise 11 cheezein save karne ki koshish ki jaye, to phir HDD/SSD par extra load parta hai aur system slow ho jata hai, isse **"Memory Leakage"** issue ho sakta hai.  

**Memory Leakage** ka matlab: jab koi app RAM use karne ke baad wo memory properly release/free nahi karta, to RAM dheere dheere full hoti jati hai aur system slow ya hang hone lagta hai. Isko theek karne ke liye kabhi kabhi system restart karna parta hai taake RAM clear ho jaye.

Zyada RAM provide karna OS ka kaam hai, taake apps smoothly chal saken.

**Extra important concepts:**
- **RAM (Random Access Memory)** temporary/volatile memory hai jab computer band hota hai to RAM ka data delete ho jata hai.
- **SSD/HDD** permanent (non-volatile) storage hai copmuter band hone ke baad bhi data save rehta hai.
- **SSD** HDD se bohot zyada fast hoti hai kyunki usmein koi moving parts nahi hote (chips par based hai), jabke HDD mein spinning disk hoti hai.
- **Cache Memory** bhi ek chota sa fast memory hota hai jo CPU ke bilkul paas hota hai, frequently use hone wala data yahan store hota hai taake CPU jaldi access kar sake. 

 
### OS File ko kese Manage karta hai

- **File** = data (jaise ek document, photo, ya video ye actual data hoti hai) 
- **Folder (Directory)** = container jisme multiple files ko organize karke rakha jata hai, aur ek folder ke andar aur folders bhi ho sakte hain.

OS ek **File System** use karta hai jo decide karta hai file kahan store hogi, kaise naam milega, aur kaise access hogi. Alag OS mein alag file systems hote hain:
- **Windows:** NTFS, FAT32
- **Linux:** ext4
- **Mac OS:** APFS

Har file ka ek unique **path/address** hota hai (jaise `C:\Users\taha\Documents\notes.txt`) jisse OS use dhoond kar open karta hai. File system ye bhi manage karta hai ke file ki **permissions** kya hain yani kaun file ko read/write/delete kar sakta hai, jo security ke liye zaroori hai.  


### OS Types

**Windows:**
- **Cost:** Paid hai — license kharidni parti hai (though kai devices pe pre-installed aati hai)
- **Performance:** General use aur gaming ke liye acha, lekin thora heavy hota hai (zyada resources leta hai)
- **Uses:** Gaming, Microsoft applications (jaise MS Word, Excel, PowerPoint), office work, general home use
- **Advantages:** Sabse zyada popular OS hai, isliye zyada software isi par support karta hai, use karna aasan hai (beginner-friendly), achi customer support milti hai
- **Disadvantages:** Paid hai, viruses/malware ka zyada khatra hota hai kyunki sabse zyada log Windows use karte hain (hackers ka bhi zyada target)

**Linux:**
- **Cost:** **Open Source** aur **Free of Cost** hai koi bhi download aur use kar sakta hai
- **Performance:** Bohot lightweight aur fast hai, kam resources mein bhi acha chalta hai (isi liye purane computers pe bhi use hota hai)    
- **Uses:** Servers chalane ke liye, programming/development, cybersecurity/ethical hacking, cloud computing
- **Advantages:** Free hai, highly customizable hai (source code khud modify kar sakte hain), bohot secure hai, viruses ka khatra kam hota hai
- **Disadvantages:** Beginners ke liye thora mushkil ho sakta hai (command line zyada use hoti hai), kam commercial software/games isko support karte hain
- Linux ka **kernel** ek person (**Linus Torvalds**) ne 1991 mein banaya tha isi wajah se ye "Linux" kehlata hai (Linus + Unix). Linux apne aap mein ek pura OS nahi, balke sirf kernel hai, jispar aage "distros" (distributions) banti hain jaise **Ubuntu, Kali Linux, Debian, Fedora**. (Ubuntu is user-friendly).  

**Hacking tools:** Nmap, Wireshark, Hydra — ye tools **Kali Linux** (jo hacking/security ke liye special distro hai) mein pre-installed milte hain, isliye ethical hackers/cybersecurity experts Linux zyada use karte hain.

**Mac OS (Apple):**
- **Cost:** Paid hai, aur sirf Apple ke hardware (MacBook, iMac) ke sath aata hai — alag se license nahi milta
- **Performance:** Bohot smooth aur stable hai kyunki Apple khud hardware aur software dono banata hai (isliye compatibility perfect hoti hai)
- **Uses:** Designing, video editing, photography, development (kyunki Unix-based hai)
- **Advantages:** Bohot secure hai, stylish design, achi build quality, creative professionals mein popular hai
- **Disadvantages:** Mehnga hai, sirf Apple devices pe milta hai, gaming ke liye utna acha nahi (kam games support karte hain)
- Mac OS **Unix-based** hai, apni stability, security aur design ke liye jana jata hai. Ye closed/proprietary system hai (source code publicly available nahi hai).


### Linux Kernel

**Kernel** OS ka sabse core/central part hota hai ye directly hardware (CPU, memory, devices) ko manage karta hai aur software ke commands ko hardware tak pohanchata hai. Ise OS ka "brain & soul" bhi keh sakte hain, kyunki bina kernel ke OS kaam hi nahi karega.
   
Linux zyada tar **server** ko chalane ke liye use hota hai kyunki ye stable, secure, aur free hai, aur lambe time tak bina crash hue chal sakta hai (jo servers ke liye bohot zaroori hai). 

Jab hum internet par koi website open karte hain, to **request** hamare device se **server** ko jati hai, server usay process karke **response wapis internet ke through** bhej deta hai. Ye poora process milliseconds mein hota hai.

**Server kya hota hai:** Server ek powerful computer hota hai jo 24/7 chalta rehta hai aur data/website/files store karke doosre computers (clients) ko provide karta hai jab wo request bhejein.

**AWS (Amazon Web Services):** Ye ek **cloud computing platform** hai jo companies ko servers rent par deta hai — matlab company ko khud apna physical server kharidne ki zaroorat nahi, wo Amazon se cloud pe space le sakti hai. Zyada tar cloud servers **Linux** par hi chalte hain, isi liye Linux server-side computing mein itna important hai. AWS jese doosre platforms bhi hain jaise **Google Cloud** aur **Microsoft Azure**.

