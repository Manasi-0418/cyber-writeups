# CTF-1

Explore carefully and uncover the hidden flag stored within.

NOTE : Flag format will be WBA{C1_flag_x7q9} or WBA{aman_crtp_123} 

Ans:- 

Tool — StegOnline

Step 1 — Download the Image 

Step 2 —  Upload Image on StegOnline 

Step 3 — Click on Show String

Step 4 — Identify the Flag

Flag — WBA{C1_flag_good_luck}

C2 - Your task is to visit the website [**https://whitebandassociates.com (opens in new tab)**](https://whitebandassociates.com/) and find the name of the server hosting the website.Once you find the server name, submit it in the following flag format:WBA{C2_flag_Servername} 

Ans:-

Target Website -  [**https://whitebandassociates.com**](https://whitebandassociates.com/) 

Tool – Netcraft Research Tool

Step 1 —  Open the Website 

Step 2 — Select Site Report

Step 3 — Paste  [**https://whitebandassociates.com**](https://whitebandassociates.com/)

Step 4 — Analyze Website Information

Step 5 — Identify Flag

Flag — WBA{C2_flag_Pepyaka}

C3 - Legends say that every treasure is guarded by a secret — the secret of the land it’s hidden in. Your mission is to uncover the hidden **Operating System** of the website [**http://testasp.vulnweb.com/ (opens in new tab)**](http://testasp.vulnweb.com/). Once you find the server name, submit it in the following flag format:WBA{C3_flag_Operating_System} 

Ans:- 

Target Website - [**http://testasp.vulnweb.com**](http://testasp.vulnweb.com/)

Tool — [censys](http://censys.io)[.io](http://censys.io) search

Step 1 — Open the Website

Step 2 —  Paste [**http://testasp.vulnweb.com**](http://testasp.vulnweb.com/) 

Step 3 — Analyze information

Step 4 — Identify Flag

Flag — WBA{C3_flag_Windows_Server}

C4 - Deep within the shadows of [**https://netleapsolutions.com/ (opens in new tab)**](https://netleapsolutions.com/) lies a hidden vault — the very heart of its knowledge: the **database. **Once you find the server name, submit it in the following flag format:WBA{C4_flag_DB_Version}

C5 - Sometimes, secrets aren’t hidden deep in the server —They're left wide open... whispered by the browser itself. Find the projectId from the DataBase configuration exposed in the JS file. URL - https://netleapsolutions.com/  Once you find the server name, submit it in the following flag format:WBA{C5_flag_projectid_641}  

C6 - A rising infosec researcher — Cyb3rT3cH (Aman Gupta) — spotted a forgotten vulnerability in one of NASA’s open directories.During passive recon, he accessed a now-removed PDF file that revealed strategic notes on a planetary surface mission.The file was once publicly available at the following location: [https://earth.jpl.nasa.gov/system/documents/files/3_ESP-A_Notes_1-28-20.fnl_rrf.pdf (opens in new tab)](https://earth.jpl.nasa.gov/system/documents/files/3_ESP-A_Notes_1-28-20.fnl_rrf.pdf)  NASA responded quickly.

The file was taken down. The path was patched. But...... Can you still retrieve it? ------------ 🧭 Your Mission: Use your web investigation skills to recover the original PDF using historical internet techniques.Once found, extract the title shown on the first page of the document. FLAG FORMAT WBA{C6_flag_Title_Sjjjjjjjj_Program-A} 

Ans :- 

Target - NASA PDF URL

Tool – Wayback Machine 

Step 1 — Open Wayback Machine

Step 2 — Paste URL 

Step 3 — 

Click on snapshot

Step 4 - 

Flag - WBA{C6_flag_Earth_Science_Program-A}

C7 - Real hackers don’t knock on the front door —they look for the **forgotten side gates**. Can you map the empire of ARESS before it shifts again? domain: aress.com . FLAG FORMAT WBA{C7_flag_aman.wba.com} 

Ans :- 

Target - [aress.com](http://aress.com)

Tool — Dnsdumpster

Step 1 - Open Dnsdumpster

Step 2 - Paste domain

Step 3 - analyze information

Flag – WBA{C7_flag_recruitment[.aress.com](http://.aress.com)}

C8- In the previous mission, you uncovered a live subdomain (the last flag you submitted). Your next task is to find the admin login page hidden somewhere under that subdomain. FLAG FORMAT WBA{C8_flag_/**/**}

Ans:- 

C9 - Not every part of a domain serves a page to browse. Some corners hold inboxes.

Some serve silence... until a user speaks through them.  On the domain: **recruitment.aress.com**  a quiet portal exists — one not meant for public eyes, but for exchanging thoughts, approvals, and secrets within. Your task is to identify the webmail platform used on this domain. No login required. No digging deep. Just name the system managing the mail behind that curtain. FLAG WBA{C9_flag_Webmailname} 

Ans:- 

Target :- [**recruitment.aress.com**](http://recruitment.aress.com)

Tool :- [censys.io](http://censys.io) search

Step 1 — 

Flag — WBA{C9_flag_Roundcube}

C10 - They say every machine has a mirror —a file that quietly echoes everything the server is and does. Rarely locked, often forgotten.Sometimes its name even sounds like its purpose.

Your exploration of: **recruitment.aress.com** leads you to such a reflection — a misplaced script that reveals version info, loaded modules, paths, and more.

Your mission:

Identify the exact PHP version running on this domain, as exposed in the server’s reflection file. FLAG WBA{C10_flag_Version_0.0.00} 

Ans:- 

Step 1 — Open the Target 

Step 2 — Open URLs like:

[https://recruitment.aress.com/phpinfo.php](https://recruitment.aress.com/phpinfo.php)

Step 3 :- Identify Version

Flag — WBA{C10_flag_Version_7.2.34}

C11 -Every script knows where it lives.And if it speaks too freely, it may reveal its home to anyone who listens.In one of your earlier discoveries on: **recruitment.aress.com **you encountered a reflective script — a misconfigured file revealing more than it should. It spoke not only of PHP’s inner workings, but also quietly disclosed its base residence — something stored in a variable often used by developers to build file paths. Look carefully in the same place where the PHP version was revealed. Your task: Extract the full absolute path where the server hosts its files, as revealed in that reflection. Flag -- WBA{C11_flag_/path/path/path_html} 

Ans:- 

Step 1 — Open the Target 

Step 2 — Open URLs like:

[https://recruitment.aress.com/phpinfo.php](https://recruitment.aress.com/phpinfo.php)

Step 3 — 

Flag — WBA{C11_flag_/home/recruitmentaress/public_html}

C12 -Every network is a story — told through whispered addresses and hidden gateways.In your journey through: **recruitment.aress.com** .you stumbled upon a reflective script — a mirror revealing much more than just the server’s face. Amidst its secrets were clues to a complex web of connections: 

The server’s own address inside its private vaults.

The contact point for the server’s overseer.

The distant visitor’s footprint.

And the secret channel through which that visitor speaks. **Your mission is to uncover these four hidden whispers:**

The internal IP address of the server.

The email address designated as the server’s administrator.

Extract each value as revealed in the server’s mirror. **YOU NEED TO SUBMIT 2 FLAGS HERE!!!  ** -- FLAG --  dont mistake the sequance of the flag and use space do add more flags ex: WBA{C12_flag_0.0.0.0} WBA{C12_flag_aman@wba.com} 

Ans:- 

Step 1 — Open the Target 

Step 2 — Open URLs like:

[https://recruitment.aress.com/phpinfo.php](https://recruitment.aress.com/phpinfo.php)

Step 3 — 

Flag :- WBA{C12_flag_172.31.42.243} WBA{[C12_flag_webmaster@recruitment.aress.com](mailto:C12_flag_webmaster@recruitment.aress.com)}

C13 -Every fortress has its scars, every system its tales of struggle. Sometimes, these stories are recorded — hidden away where only the curious dare to look. In the depths of your exploration of:**recruitment.aress.com** you uncover a forgotten diary — a place where the server notes its missteps and errors.Though meant to be private, it lies exposed, revealing clues that could unravel hidden truths.Your task:Find this diary of errors **location / path** and uncover one significant error message logged within. FLAG ---WBA{C13_flag_/path_path} 

Ans: -

C14 -Every grand structure has its dark corners — places where forgotten files collect dust, and secrets lie unguarded. While exploring the corridors of **recruitment.aress.com,** you noticed a door left ajar — not a page, not a script, but a raw view into the **backend itself**. A **directory** meant to be **hidden**, but left open to those who know where to look. Inside this hidden drawer, among scattered logs and **misnamed files**, you come across something **critical: the server’s access keys to its heart** — the **database**. Your mission: locate the credentials that connect this site to its database and submit the full username and password as one combined string. FLAG --- WBA{C14_flag_username:password}  

C15-Every domain stands guarded by silent watchers—**name servers** that decide who may enter. While exploring **whitebandassociates.com**, your task is to identify one such gatekeeper that routes its digital path. Those who know how to question the roots of a domain will find the answer.  FLAG-- WBA{C15_flag_nameserver} 

Ans:- 

Target – [**whitebandassociates.com**](http://whitebandassociates.com)

Tool —**  dnsdumpster**

Flag — WBA{C15_flag_ns0[.wixdns.net](http://.wixdns.net)}

C16 -Every domain has a ticking clock. Explore **TechnoPk.com** and uncover the exact date when its digital lease runs out. Flag -- WBA{C16_flag_yyyy-mm-dd} 

Ans:-

Target:-**TechnoPk.com**

Tool – [https://whois.domaintools.com/](https://whois.domaintools.com/)

Step 1 –

Flag :-- WBA{C16_flag_2026-03-13}

C17- A suspicious string was recovered from the remnants of a compromised login system: **21232f297a57a5a743894a0e4a801fc3**. Though it appears cryptic, it hides a common identity protected by an old-school hashing algorithm. Your task is to reveal the original plaintext behind this hash. Flag  WBA{C17_flag_crackedhash} 

Ans:- 

Target — **21232f297a57a5a743894a0e4a801fc3**

Tool :- [https://crackstation.net/](https://crackstation.net/)

Flag- WBA{C17_flag_admin}

C18 - After completing her internship, ** Nikita Gaikwad** received an offer from an institute named **NITS**, located in **Nashik** — the same place where ex-trainer **Aman Gupta** once worked. Your task is to uncover the **salary amount** offered to her by NITS after her internship. Use only publicly available sources and digital traces. 

Flag-- WBA{C18_flag_1000000} 

Ans:- 

Search in browser - "nikita gaikwad" "nits" "mrs. mrunal a. dhahale"

Flag - WBA{C18_flag_180000}

C19 - While mapping the leadership of NITS, your focus shifts to **Mrs. Mrunal A. Dhahale**, the Director of the institute. Through internal and ethical sources, you gain access to a partially redacted phone number — only the last three digits are visible: **055**. Your mission is to identify her **full  PRIVATE  contact number** used for communication, strictly for OSINT training purposes and with prior consent. FLAG- WBA{C19_flag_XXXXXXX055} 

Ans:- 

Search on browser–"055" "nits" "mrs. mrunal a. Dhahale"

Flag— WBA{C19_flag_9273735055}

C20-While analyzing suspicious network activity from a compromised machine, your team detected an outgoing connection to the IP address 106.213.80.208. As part of the initial reconnaissance phase, your task is to perform OSINT (Open Source Intelligence) and determine which organization owns or is responsible for this IP address. This challenge will test your ability to use public tools and databases to trace IP ownership. You must find the registered organization name associated with the IP and submit it in the required flag format. WBA{C20_flag_Aaaaa_Aaaaa_Aaa} 

Ans:- 

Target – 106.213.80.208

TooltollToTtoolo

Flag – WBA{C20_flag_Bharti_Airtel_Ltd}
