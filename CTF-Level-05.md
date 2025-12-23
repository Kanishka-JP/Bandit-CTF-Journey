🛰️ Bandit Stage 05 ➜ 06  

🧷 Access Info  
Username: bandit5  
Server: bandit.labs.overthewire.org  
Port: 2220  

🎯 Challenge Overview  
Inside the `inhere` directory are many nested subdirectories containing numerous files.  
Only one file meets all the following conditions:  
- Human-readable  
- Exactly 1033 bytes in size  
- Not executable  
The goal is to identify this file and retrieve the password for the next level.

🖼️ Terminal Snapshot  
Bandit Level 05 Screenshot  

🧭 How It Was Solved  
Manually checking each file would be inefficient due to the number of directories.  
The `find` command is used to recursively search through all subdirectories while applying filters for file type, size, readability, and execution permission.  
This precisely isolates the single file that matches all required conditions.

💻 Commands Executed  
ls  
cd inhere  
find . -type f -size 1033c -readable ! -executable  
cat ./maybehere07/.file2  

🔐 Password Retrieved  
HWasnPhtq9AVKe0dmk45nxy20cvUa6EG  

📘 Explanation  
The `inhere` directory contains multiple subfolders with many files.  
The `find` command searches through all directories recursively.  
Filters are applied to match only regular files with an exact size of 1033 bytes, readable permission, and no execute permission.  
The matching file is a hidden file located inside a subdirectory.  
Using `cat` displays its contents, revealing the password for the next level.

🧠 Key Takeaway  
This level reinforces:  
- Recursive file searching with `find`  
- Filtering files based on size and permissions  
- Identifying hidden files in Linux  
- Efficient command-line investigation techniques  
