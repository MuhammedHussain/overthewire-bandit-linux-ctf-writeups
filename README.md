# overthewire-bandit-linux-ctf-writeups
Documenting my learning journey, terminal commands, and step-by-step solutions for OverTheWire Bandit challenges.

## Levels 0–6 Quick Recap
Progressed through levels 0 to 6 by mastering core Linux CLI commands (cat, ls, file, grep, base64, tr). Key challenges involved filtering file sizes, finding unreadable/hidden files inside inhere directories, and parsing compressed archives.

## Bandit Level 6 → Level 7
### Objective
Find the password for the next level stored somewhere on the server matching specific file attributes:
- User owner: bandit7
- Group owner: bandit6
- File size: 33 bytes (33c)

### Solution Walkthrough
#### 1. Search the File System:
   Execute the find command from the root directory (/) with strict parameter filtering while redirecting permission errors (2>/dev/null):

Command:
find / -user bandit7 -group bandit6 -size 33c 2>/dev/null 

Tips:
  There are two Standard Output Channels in Linux. 
    1. Standard Output Stdout
    2. Standar Error Stderr

    2>/dev/null : Meaning of this is get the output errors and redirect all to the black hole. 
    
#### 2. Flag Retrieval:
   Read the output path returned by find using cat:
 
 Command:
 cat /var/lib/dpkg/info/bandit7.password

 


