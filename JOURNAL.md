# Journal

A curated progress log of my journey through the roadmap.
Raw notes and reflections are kept privately.

---

## Entry 001 — June 2026

**Phase:** Pre-university  
**Focus this week:** Setting up professional infrastructure

### What I did
- Created GitHub profile and career-roadmap repository
- Drafted and refined README with intentional framing
- Researched the distinction between public portfolio and private journal

### One thing that made me think
Writing a GitHub bio forced me to be precise about where I actually 
am versus where I'm going. "Incoming" versus "undergraduate" — 
a small word that matters a lot when integrity is part of the career 
you're building.

---

## Entry 002 — June 2026

Completed OverTheWire Bandit Level 0 using the Linux command line interface. Once I viewed the command as one big address rather than separating the port, user, and host, it finally clicked. Targeting Level 1 next.

---

## Entry 003 — July 2026

Using my Linux terminal, I finished Bandit Level 1 from OverTheWire. The password was found at the home directory; I could see that with the `ls` command and I could use the `cat` command to output what was in the file. The questions about locations and the permission system made sense. Proceeding to Level 2. 

---

## Entry 004 — July 2026

I finished Bandit Level 2 from OverTheWire using the Linux command line interface. The file with the name `-` did not get recognized as it was treated as a special input and worked when i added `./` giving it an explicit path. On to Level 3.

---

## Entry 005 — September 2026

Officially started MCS Year 1 at MMU. Installed WSL2 and Ubuntu on my laptop. Python 3.14.4 and Git 2.53.0 running. Resumed OverTheWire Bandit — targeting Level 3 this week. First university lectures begin this week.

---

## Entry 006 — October 2026

Completed OverTheWire Bandit Level 3 via Linux terminal. The file name had spaces and started with `--` and only worked once I wrapped it in quotes (so the shell treated it as one argument) and used `./` for the current directory. This helped me understand how the shell reads file names. Next: Level 4.

---

## Entry 007 — October 2026

Completed OverTheWire Bandit Level 4. I learned how to navigate into a directory using `cd`, and how `ls -a` reveals hidden files that a normal `ls` does not show. I also learned the difference between `.` (current directory) and `..` (parent directory). The hidden file was named `...Hiding-From-You`, which I read using its explicit path.

---

## Entry 008 — October 2026

Completed OverTheWire Bandit Level 5. The password was stored in the only human-readable file inside the `inhere` directory. I learned how to use the `file` command to identify file types and the `*` wildcard to apply a command to multiple files at once. Using `file ./` let me check all the files and identify the one containing ASCII text, which I then read to get the password.

---

## Entry 009 — October 2026

Completed OverTheWire Bandit Level 6. The password was hidden somewhere inside the `inhere` directory among many files and directories, with specific properties: it had to be human-readable, exactly 1033 bytes, and not executable. I learned how to use `find` recursively and combine multiple conditions to narrow down a search. I used `-type f` to target regular files, `-readable` for readable files, `! -executable` for non-executable files, and `-size 1033c` to match the exact file size. This level helped me understand how command-line tools can filter large amounts of data using multiple conditions instead of checking everything manually.

---

## Entry 010 — October 2026

Completed OverTheWire Bandit Level 7. The password was stored somewhere on the server in a 33-byte file owned by user `bandit7` and group `bandit6`. I learned how to use `find` from the root directory (`/`) and filter results using file ownership with `-user` and `-group`, along with `-size` for the exact file size. I also learned the difference between relative and absolute paths. An absolute path such as `/var/lib/dpkg/info/bandit7.password` can be accessed directly regardless of my current directory, so I do not need to navigate through each parent directory first. This level showed me how much more efficient targeted searching can be than manually exploring the filesystem.

---

## Entry 011 — October 2026

Completed OverTheWire Bandit Level 8. The password was stored in `data.txt` next to the word `millionth`. I learned how to use `grep` to search for specific text within a file. I also reinforced the difference between locating a file and being able to access its contents: I initially found `/home/bandit7/data.txt` while logged in as `bandit6`, but could not read it because of file permissions. After logging into `bandit7`, I could access the file and use `grep` to find the required line. This level helped me understand both basic text searching and Linux file permissions.

---

## Entry 012 — October 2026

Completed OverTheWire Bandit Level 9. The password was the only line in `data.txt` that occurred exactly once among many repeated lines.

I learned how to combine multiple command-line tools into a pipeline to process data efficiently. I used `sort` to group identical lines together, `uniq -c` to count how many times each line occurred, and `grep` to filter the output and find the line whose count was exactly 1.

I also learned my first practical regex concepts. `^` represents the beginning of a line, while `*` means zero or more occurrences of the preceding character. I used these together to match the count at the beginning of the `uniq -c` output. I initially used `grep '^ *1'`, which also matched `10`, because both begin with `1`. Adding a space after the `1` — `grep '^ *1 '` — made the pattern match a count of exactly 1.

This level reinforced the idea that Linux commands can be chained together, with each command performing one specific task and passing its output to the next. It also introduced me to using regular expressions to make text filtering more precise.

---
