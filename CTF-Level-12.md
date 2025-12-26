## 🛰️ Bandit Level 12 ➜ 13

### 🧷 Access Info
**Username:** bandit12  
**Password:** Obtained from previous level  
**Server:** bandit.labs.overthewire.org  
**Port:** 2220  

---

### 🎯 Challenge Overview
The password for the next level is stored in the file `data.txt`.  
The file contains **multiple layers of compression and encoding** (gzip, bzip2, tar, and hex).  
The objective is to repeatedly identify the file type, extract or decode it step by step, and finally retrieve the password.

---

### 🖼️ Terminal Snapshot
![Bandit Level 12 Screenshot](screenshots/level12.png)

---

### 🧭 How It Was Solved
A temporary working directory is created to safely extract files.  
The file type is checked at every stage using the `file` command.  
Depending on the detected format, appropriate tools such as `xxd`, `gzip`, `bzip2`, and `tar` are used to decode or extract the data.  
This process is repeated multiple times until a readable ASCII file containing the password is obtained.

---

### 💻 Commands Executed
- `mkdir /tmp/ctf`  
- `cp data.txt /tmp/ctf`  
- `cd /tmp/ctf`  
- `file data.txt`  
- `xxd -r data.txt > data`  
- `file data`  
- `mv data data.gz`  
- `gzip -d data.gz`  
- `file data`  
- `mv data data.bz2`  
- `bzip2 -d data.bz2`  
- `file data`  
- `mv data data.tar`  
- `tar -xvf data.tar`  
- `file data5.bin`  
- `mv data5.bin a.tar`  
- `tar -xvf a.tar`  
- `file data6.bin`  
- `mv data6.bin ak.bz2`  
- `bzip2 -d ak.bz2`  
- `file ak`  
- `mv ak ak.tar`  
- `tar -xvf ak.tar`  
- `file data8.bin`  
- `mv data8.bin ak.gz`  
- `gzip -d ak.gz`  
- `file ak`  
- `cat ak`  

---

### 🔐 Password Retrieved
**F05dwFsc0cbaIiH0h8J2euks2vdTDwAn**

---

### 📘 Explanation
- `file` is used repeatedly to identify the current file format.  
- `xxd -r` reverses hex encoding back to binary data.  
- `gzip`, `bzip2`, and `tar` are used based on the detected compression type.  
- Files are renamed appropriately so extraction tools recognize the format.  
- After all layers are removed, the final file is readable ASCII text containing the password.

---

### 🧠 Key Takeaway
- Identifying file formats using `file`  
- Handling multi-layer compression and encoding  
- Using extraction tools (`gzip`, `bzip2`, `tar`) effectively  
- Importance of step-by-step analysis in complex file challenges  
