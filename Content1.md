# Computer Communication & Cybersecurity - Notes

## 1. Communication ki 2 types

- Internal: Computer ke andar hoti hai (CPU, RAM, ROM, Input, Output ke beech)
- External: Computer se bahar, network ke through (jese Internet). DNS isi mein aata hai.

## 2. Internal parts kya karte hain

- Data: Raw information jo computer process karta hai
- RAM: Temporary memory, sirf tab tak jab computer ON ho 
- ROM: Permanent memory, computer start karne ki fixed instructions
- Input: Data andar aata hai (keyboard, mouse)
- Output: Result dikhta hai (screen, printer)
- CPU: Sab parts ke beech "middle man", processing karta hai
- OS (Windows/Linux): Sab kuch manage karta hai

## 3. User OS se kese baat karta hai 

Communication through os can be done in two ways:

GUI: Icons, buttons, windows - click karke command do. Beginners ke liye easy. Example: Windows Desktop.

CLI: Typed text commands se control karo. Ek baar seekh lo to fast hota hai. Example: Linux Terminal, CMD.

## 4. CLI ke common commands (command line interface)

- pwd (Print Working Directory) → batata hai abhi kis folder mein ho
- ls (List) → files aur folders dikhata hai
- cd Desktop (Change Directory) → Desktop folder mein le jata hai
- cat example.txt (Concatenate) → file ka content dikhata hai
- touch newfile.txt (Touch) → nayi empty file banata hai

Example use:
pwd → current location
ls → files/folders ki list
cd Desktop → Desktop mein jao
cat example.txt → file ka content dekho

## 5. GUI kahan use hota hai  (graphical user interface)

- Software Development
- Data handling aur analysis
- Security tasks

## Flow (sab kese connect hota hai)

Input Device → CPU (processing) → RAM/ROM (data/instructions) → Output Device
Uske upar: Operating System sab manage karta hai
Aur user GUI ya CLI se interact karta hai

## 6. External Communication - DNS

DNS ek website ka naam (google.com) ko uske IP address mein convert karta hai, taake connection ban sake.

Example: Jab tum google.com type karte ho, DNS use IP address mein badal deta hai. 

agr ip likh k b search kro to website open ho jati hai , iska matlab hai k website ip se b chalti hai , lakin har website ka ip yad rakhna mushkil hai , islye DNS use hota hai  is liya user ko name yad rkhna hota hai or dns usko ip m convert kr deta hai isko dns lookup kahte hai

## DNS Lookup kese kaam karta hai

1. Browser pehle apna cache check karta hai (pehle visit kiya tha ya nahi)
2. Agar cache mein mil jaye, website to khul jati hai (fast)
3. Agar na mile, to DNS lookup start hota hai:

- Client: tumhara device, request bhejta hai jo dns server ko jata hai 
- Router: request internet ko forward karta hai
- Resolver: ISP ka server jo DNS query handle karta hai
- Root Server: query ko sahi direction mein point karta hai
- TLD Server: domain type handle karta hai (.com, .org)
- Auth Server: final, correct IP address deta hai

## 7. Quick Recap

- Internal Communication → Computer ke andar (CPU, RAM, ROM, Input, Output)
- External Communication → Network ke zariye, do devices connect (DNS included)
- GUI → Icons aur mouse clicks se interaction
- CLI → Typed commands se interaction
- DNS → Website ka naam IP address mein convert karta hai
- Cache → Pehle visit ki gayi cheez store karta hai, dobara dhundna nahi padta
