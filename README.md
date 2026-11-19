# week3-project-cybersecurity-with-networkwalks-B084-password-cracking
Password Cracking with JtR and Networwalks tools

## Project Overview

This lab focused on password security testing through practical password-cracking exercises. Building on earlier modules covering footprinting, reconnaissance, and network scanning, this week shifted focus from information gathering to testing the strength of credentials and understanding how password hashes can be attacked. The exercise used three main tools: John the Ripper (JtR) and its graphical front-end Johnny for cracking a password-protected file, and the NetworkWalks Hash Calculator and NetworkWalks Password Cracker for generating and reversing hash values. Together, these tools demonstrate the full lifecycle of password-based authentication: how passwords are stored as hashes, and how weak hashes or weak passwords can be recovered by an attacker.

## Project Objectives
 - Understand how password-protected files store and verify credentials internally.
 - Learn to extract crackable hash data from a protected file using the appropriate John the Ripper helper script.
 - Use John the Ripper and Johnny to perform dictionary and/or brute-force attacks against a password hash.
 - Use the NetworkWalks Hash Calculator to generate hash values from known inputs and observe how hashing algorithms behave.
 - Use the NetworkWalks Password Cracker to attempt to recover a plaintext password from a hash.
 - Compare cracking speed and success rate across different password complexities.
 - Document the entire process, including evidence, results, and recommendations, in a professional format.

## Purpose of the Lab

Password cracking labs exist to show, firsthand, why weak passwords and poor hashing practices remain one of the most common ways attackers gain unauthorized access. In a real penetration test, cracked credentials can lead directly to account takeover, lateral movement, or privilege escalation. This lab’s purpose was to build practical skill in:

 - Recognizing which parts of a file or system store password-verification data.
 - Using industry-standard tools (JtR) alongside simplified web-based tools (NetworkWalks calculators) to understand both the manual and automated sides of hash cracking.
 - Appreciating the real-world time and effort difference between a strong password and a weak one.
 - Reinforcing that these techniques are only ever applied in an authorized, controlled lab environment.

## Procedures

### File preparation
Identified the password-protected file to be used as the target and confirmed it was an authorized lab exercise.
### Hash extraction
Used the relevant John the Ripper helper script or a hash extractor website to extract the file’s password-verification data into a crackable hash format (for example, zip2john, pdf2john.pl, or office2john, depending on file type).

![image alt](https://github.com/hajartouab27-prog/week2-project-cybersecurity-with-networkwalks-B084-password-cracking/blob/main/hash_extractor.png)

### Cracking with John the Ripper
Ran John the Ripper against the extracted hash, first using a wordlist attack and then, if necessary, incremental/brute-force mode. Monitored progress and recorded the time to crack.

### Cracking with Johnny
Repeated the process using Johnny, JtR’s graphical interface, to compare usability and workflow against the command-line tool.

![image alt](https://github.com/hajartouab27-prog/week2-project-cybersecurity-with-networkwalks-B084-password-cracking/blob/main/Johny_interface.png)
![image alt](https://github.com/hajartouab27-prog/week2-project-cybersecurity-with-networkwalks-B084-password-cracking/blob/main/file1.png?raw=true)

### Hash generation with NetworkWalks Hash Calculator
Entered sample plaintext values and generated their corresponding hashes (e.g., MD5, SHA-1, SHA-256) to observe how different algorithms produce different outputs and how even a one-character change in input drastically changes the hash (the avalanche effect).

![image alt](https://github.com/hajartouab27-prog/week2-project-cybersecurity-with-networkwalks-B084-password-cracking/blob/main/Networkwalks_hash_extractor.png)

### Hash cracking with NetworkWalks Password Cracker
Submitted hash values to the tool to attempt plaintext recovery, comparing results against known password lists and common hash databases.

![image alt](https://github.com/hajartouab27-prog/week2-project-cybersecurity-with-networkwalks-B084-password-cracking/blob/main/Networkwalks-tool.png)
![image alt](https://github.com/hajartouab27-prog/week2-project-cybersecurity-with-networkwalks-B084-password-cracking/blob/main/file4.png)

### Analysis and documentation
Compared cracking times and success rates across tools and password complexities, took screenshots as evidence, and compiled findings into a structured report with mitigation recommendations.

### Other cracked files

![image alt](https://github.com/hajartouab27-prog/week2-project-cybersecurity-with-networkwalks-B084-password-cracking/blob/main/file2.png)
![image alt](https://github.com/hajartouab27-prog/week2-project-cybersecurity-with-networkwalks-B084-password-cracking/blob/main/file3.png)

## What I Learned

Password-protected files don’t store the password itself. They store verification data derived from it, and tools like JtR’s *2john scripts extract that data into a crackable format.
Hashing is one-way by design, but a hash is only as strong as the password behind it. A weak or common password can be recovered quickly regardless of the hashing algorithm used.
Wordlist attacks are dramatically faster than brute-force against predictable passwords, which highlights why password reuse and common patterns are so dangerous.
Salting and iteration counts (used in formats like Office and PDF encryption) significantly slow down cracking attempts compared to unsalted, single-pass hashes.
Graphical tools like Johnny lower the barrier to entry for the same techniques available in the JtR command line, which is worth keeping in mind from a defensive perspective.
Simple web-based hash calculators and crackers are useful for quickly understanding hash behavior, but they rely on precomputed databases and are far less powerful than dedicated cracking tools against custom or complex hashes.
The single biggest defensive takeaway: strong, unique passphrases combined with modern, salted, iterated hashing algorithms (and multi-factor authentication) are what actually make cracking impractical.

## Security and Ethical Considerations

All cracking activities were performed on a file and environment I was explicitly authorized to test, within the scope of the internship program.
None of the tools, techniques, or hashes used in this exercise were applied to any system, file, or account outside this authorized lab environment.
Password-cracking skills carry real potential for harm if misused; applying them without authorization against real systems is illegal in virtually all jurisdictions and a clear violation of ethical hacking principles.
Any cracked credentials, hash values, or screenshots containing sensitive data were handled carefully and are not shared outside the scope of this educational documentation.
The report emphasizes responsible disclosure and documentation practices consistent with professional penetration testing standards, focusing on risk analysis and mitigation rather than exploitation for its own sake.
Recommendations for defense are included alongside the offensive findings, consistent with the dual purpose of this kind of exercise: understanding attacker techniques in order to build better defenses.

## Author

**Project completed as part of the Cybersecurity Internship Program at NetworkWalks — Batch B084.**

This repository documents the practical work completed during the third week's project of the program.

## Project Information

| Category | Details |
|---|---|
| Program | Cybersecurity Internship at NetworkWalks |
| Batch | B084 |
| Week | 03 |
| Project | Cybersecurity & Password Cracking |
| Main Tools | JtR John & Johny, Kali Linux, NetworkWalks tools |
| Repository | GitHub |

