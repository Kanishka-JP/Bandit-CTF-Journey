## 🛰️ Bandit Level 17 ➜ 18

### 🧷 Access Info
**Username:** bandit17  
**Password:** Obtained from previous level  
**Server:** bandit.labs.overthewire.org  
**Port:** 2220  

---

### 🎯 Challenge Overview
The home directory contains two files: `passwords.new` and `passwords.old`.  
Both files are nearly identical, but **one line differs** between them.  
The objective is to compare the two files and identify the **correct password**, which appears as the **second entry in the diff output**.

---

### 🖼️ Terminal Snapshot
![Bandit Level 17 Screenshot](screenshots/level17.png)

---

### 🧭 How It Was Solved
The `diff` command is used to compare the contents of `passwords.new` and `passwords.old`.  
The output shows two different lines:
- Lines starting with `<` belong to `passwords.new`
- Lines starting with `>` belong to `passwords.old`

The **second line (prefixed with `>`)** is the valid password.

---

### 💻 Commands Executed
- `ls`  
- `diff passwords.new passwords.old`  

---

### 🔐 Password Retrieved
**pGozC8kOHLkBMOaL0ICPvLV1IjQ5F1VA**

---

### 📘 Explanation
- `ls` confirms both password files are present.  
- `diff` compares the two files line by line.  
- The first line (`<`) shows the password from `passwords.new`.  
- The second line (`>`) shows the password from `passwords.old`.  
- The required password is the **second one**, starting with `pGoz`.

---

### 🧠 Key Takeaway
- Comparing files using `diff`  
- Understanding `diff` output symbols (`<` and `>`)  
- Importance of command order in comparisons  
- Carefully identifying the correct data from similar outputs  
