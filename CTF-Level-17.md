## 🛰️ Bandit Level 17 ➜ 18

### 🧷 Access Info
**Username:** bandit17  
**Password:** Obtained from previous level  
**Server:** bandit.labs.overthewire.org  
**Port:** 2220  

---

### 🎯 Challenge Overview
The home directory contains two files: `passwords.old` and `passwords.new`.  
Both files are almost identical, but **one line is different**.  
The objective is to compare these two files and identify the **changed line**, which is the password for the next level.

---

### 🖼️ Terminal Snapshot
![Bandit Level 17 Screenshot](screenshots/level17.png)

---

### 🧭 How It Was Solved
The directory contents are checked to confirm the presence of both password files.  
The `diff` command is used to compare the two files line by line.  
The output highlights the line that exists only in the newer file, revealing the password for the next level.

---

### 💻 Commands Executed
- `ls`  
- `diff passwords.old passwords.new`  

---

### 🔐 Password Retrieved
**x2gLTTjFwMOhQ8oWNbMN362QKxfrQgI0**

---

### 📘 Explanation
- `ls` lists the files in the directory and confirms both password files are present.  
- `diff` compares the contents of the two files.  
- Lines prefixed with `<` belong to `passwords.old`.  
- Lines prefixed with `>` belong to `passwords.new`.  
- The line marked with `>` is the updated password used to access Level 18.

---

### 🧠 Key Takeaway
- Comparing files using `diff`  
- Identifying changes between similar files  
- Understanding diff output symbols (`<` and `>`)  
- Efficiently extracting meaningful differences from files  
