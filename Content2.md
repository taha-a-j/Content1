# CPU, Memory & Buses

## Memory Types aur CPU ka basic kaam

### Volatile vs Non-Volatile Memory

- **RAM** : Volatile hoti hai — matlab power off hone par is ka data delete ho jata hai.
- **SSD** : Non-volatile hoti hai — matlab power off hone k baad bhi is ka data safe rehta hai.

### CPU, RAM aur SSD ka relation

- CPU zyada kaam **RAM** k sath karwata hai (RAM se data lekar process karta hai).
- Jab hum koi data change karte hain (jaise kisi file ko edit karna), to yeh kaam **CPU aur SSD** k between  bhi hota hai.
- CPU RAM ko task **assign** karta hai, aur RAM aage SSD se related kaam karti hai.
- Yeh sara process direct nahi hota — beech mein CPU ki speed aur **cache** ka role hota hai, jo cheezon ko fast karta hai.

### Buses (CPU aur RAM k darmiyan lines)

- CPU aur RAM k darmiyan data **bus** k zariye travel karta hai (bus ek "rasta" hai jahan se data guzarta hai).
- CPU aur RAM k darmiyan total **3 lines (buses)** hoti hain:

  1. **Address Bus** — yeh batata hai k data **"kahan"** hai ya kahan jana hai (location bataata hai).
  2. **Data Bus** — yeh **actual data** ko transfer karta hai, aur yeh **dono directions** (two-way) mein travel kar sakta hai.
  3. **Control Bus** — yeh batata hai k **"kya karna hai"** (yani operation kya hoga — read karna hai ya write karna hai).

## CPU ka internal kaam aur data traveling system 

### CPU ki apni fast memory — Register

- CPU k andar ek **Register** hota hai, jo CPU ki sabse **fast memory** hoti hai.
- Register data ko temporarily store karta hai jab CPU us par kaam kar raha hota hai.

### RAM se CPU tak data kaise jata hai

- Jab hum koi kaam start karte hain (jaise koi file open karna), pehle system **RAM** ko check karta hai.
- Agar data RAM mein pehle se maujood hai, to wahin se mil jata hai.
- Agar RAM **empty** hai (data nahi hai), to phir system **SSD** se data leta hai.
- SSD se data ek certain **path** se guzar kar RAM tak pohanchta hai, aur RAM us data ko **fetch** karti hai.
- Uske baad **CPU** us data ko:
  1. **Fetch** karta hai (data ko le kar aata hai),
  2. **Decode** karta hai (samajhta hai k kya karna hai),
  3. **Execute** karta hai (actual kaam perform karta hai).

Yeh poora cycle **Fetch → Decode → Execute** kehlata hai, jo CPU baar baar repeat karta hai.

### Example: Calculation aur Result Store hona

- Jab CPU koi simple calculation karta hai (jaise addition, 5 + 8), to result nikalne k baad wo:
  - Pehle **Register** mein store hota hai, "13"
  - Phir **RAM** mein store hota hai,
  - Agar permanent save karna ho to aakhir mein **SSD** mein store ho jata hai.

### example (Ctrl+S)

- Jab hum kisi **Word file** par kaam kar rahe hote hain Word file mein type karte hain →  data 
abhi sirf RAM mein hai (temporary) hota hain

Ager **Ctrl+S** dabate hain → CPU us data ko RAM se leta hai aur SSD par write kar deta hai.
Ab wo data **(SSD)**mein permanently save ho gaya (RAM mein nahi).
Agar**Ctrl+S** nahi dabaein aur computer band ho jaye, to RAM ka wo data delete ho jayega, kyun k RAM kabhi permanent nahi hoti.

RAM hamesha temporary hi store karti hai — chahe save **ctrl+s** karein ya na karein, 
RAM ka kaam sirf temporary storage hota hai jab tak power on hai. **RAM** kabhi bhi "permanent" nahi hoti.

Jo cheez permanent karti hai wo **Ctrl+S** ka action hai — jo data RAM mein (temporary) tha, 
us data ki ek copy SSD mein likh di jati hai. wo copy jo SSD mein gayi, wahi permanent ban jati hai 
(kyun k SSD **on-volatile** hai,power off hone k baad bhi wo data rehta hai).

## ROM aur BIOS

- **ROM** ek type ki memory hoti hai.
- **BIOS** ek **code/program** hai jo is **ROM** k andar store hota hai.
- Yeh BIOS computer **start hote hi sabse pehle chalta hai**, aur basic instructions deta hai taake system boot ho sake. 

**BIOS (Basic Input Output System)**

**BIOS** ek chota sa program/firmware hota hai jo ROM (ya kabhi kabhi ek chip jise EEPROM/Flash kehte hain) k andar store hota hai.
Jab hum computer power button dabate hain, sab se pehle **BIOS** hi chalta hai — RAM, operating system, ya kisi bhi software se pehle.
**BIOS** ka main kaam yeh hota hai:

**POST** (Power-On Self Test) karta hai — yani check karta hai k computer k saare parts 
(RAM, keyboard, hard disk, etc.) sahi se kaam kar rahe hain ya nahi.
Agar sab theek ho, to BIOS operating system ko dhundta hai (jaise Windows) jo storage (SSD/HDD) mein hota hai.
Phir wo operating system ko load karna start karta hai, taake computer aage boot ho sake.


Simple: **BIOS** ek "sabse pehla worker" hai jo system on hote hi jaag jata hai,
sab kuch check karta hai, aur phir baaki system (OS) ko jagata hai taake computer use karne k liye ready ho jaye.

## Example:
Jaise koi ghar ka chowkidar subah sabse pehle uthta hai, ghar k saare darwaze/lights check karta hai **(POST)**, 
phir baaki ghar walon **(operating system)** ko jaga kar apna kaam start karwata hai
bilkul waisay hi **BIOS** computer k saath karta hai.
