## 🛰️ Bandit Level 24 ➜ 25

### 🧷 Access Info
Username: bandit24  
Password: Obtained from previous level  
Server: bandit.labs.overthewire.org  
Port: 2220  

### 🎯 Challenge Overview
A program is provided that checks a **secret numeric PIN** along with the current user’s password.  
The correct PIN is unknown and must be discovered.  
The objective is to **brute-force the PIN** by repeatedly supplying the correct password combined with possible PIN values until the program accepts the input and reveals the password for the next level.

### 🖼️ Terminal Snapshot
![Bandit Level 24 Screenshot](screenshots/level24.png)

### 🧭 How It Was Solved
The pin-checking program requires two inputs on a single line:  
1. The current password for `bandit24`  
2. A numeric PIN  

A brute-force script is created to try all possible PIN combinations automatically.  
The script loops through PIN values, supplies each along with the correct password, and checks the output.  
Once the correct PIN is found, the program responds with the password for the next level.

### 💻 Commands Executed
cd /tmp  
nano brute.sh  
chmod +x brute.sh  
./brute.sh  

### 🔐 Password Retrieved
iCi86ttT4KSNe1armKiwbQNmB3YJP3q4

### 📘 Explanation
The checker program validates both the password and the PIN together.  
Manual guessing is impractical due to the number of possible PIN combinations.  
By automating the process with a shell script, each PIN is tested rapidly.  
When the correct combination is supplied, the program confirms success and outputs the password for Bandit Level 25.

### 🧠 Key Takeaway
Brute-force attacks can be automated using simple scripts.  
Programs that rely on PIN-based security are vulnerable without rate limiting.  
Automation is a powerful technique in security testing and CTF challenges.  
Understanding program input behavior is essential for exploitation.
