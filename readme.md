# Linux Commands and Concepts

---

## 1. `pwd` - Print Working Directory
**Description:** Shows the full path of the current directory.  
**Examples:**
- `pwd`  
  *Example Output:* `/home/user/documents`
- `pwd -P`  
  Displays the physical directory, avoiding symlinks.  
  *Example Output:* `/home/user/documents`
- `pwd -L`  
  Displays the logical path with symlinks (default).  
  *Example Output:* `/home/user/../documents`

---

## 2. `ls` - List Files
**Description:** Lists files in a directory.  
**Examples:**
- `ls`  
  *Example Output:* `file1.txt  file2.txt  folder`
- `ls -lh`  
  Lists files with detailed information (size, permissions, etc.).  
  *Example Output:* `-rw-r--r-- 1 user user 1.2K Sep  1 12:00 file1.txt`
- `ls -a`  
  Shows hidden files.  
  *Example Output:* `file1.txt  .hiddenfile  folder`

---

## 3. `cd` - Change Directory
**Description:** Changes the current directory.  
**Examples:**
- `cd /path/to/directory`  
  *Example:* Changes to `/path/to/directory`
- `cd ..`  
  Moves up one directory.  
  *Example:* Moves to `/path/to` from `/path/to/directory`
- `cd ~`  
  Changes to the user's home directory.  
  *Example:* Changes to `/home/user`
- `cd -`  
  Switches back to the previous directory.  
  *Example:* Returns to `/home/user` from `/var/log`

---

## 4. `mkdir` - Create Directory
**Description:** Creates a new directory.  
**Examples:**
- `mkdir myfolder`  
  *Example:* Creates `/home/user/myfolder`
- `mkdir -p /path/to/folder`  
  Creates nested directories.  
  *Example:* Creates `/path/to/folder`, including intermediate directories.

---

## 5. `cp` - Copy Files
**Description:** Copies files or directories.  
**Examples:**
- `cp file1.txt /backup/`  
  *Example:* Copies `/home/user/file1.txt` to `/home/user/backup/`
- `cp -p file1.txt /backup/`  
  Preserves file permissions.  
  *Example:* Copies `/home/user/file1.txt` while preserving permissions
- `cp -r folder/ /backup/`  
  Recursively copies a directory and its contents.  
  *Example:* Copies `/home/user/folder/` to `/home/user/backup/folder/`

---

## 6. `mv` - Move or Rename Files
**Description:** Moves or renames files or directories.  
**Examples:**
- `mv file1.txt file2.txt`  
  *Example:* Renames `/home/user/file1.txt` to `/home/user/file2.txt`
- `mv file1.txt /backup/`  
  *Example:* Moves `/home/user/file1.txt` to `/home/user/backup/`
- `mv -v file1.txt /backup/`  
  Verbosely shows the move operation.  
  *Example Output:* `‘file1.txt’ -> ‘/backup/file1.txt’`
- `mv -n file1.txt /backup/`  
  Prevents overwriting existing files.  
  *Example:* If `/backup/file1.txt` exists, it will not be overwritten.
- `mv -vn file1.txt /backup/`  
  Verbosely and without overwriting.  
  *Example Output:* `‘file1.txt’ -> ‘/backup/file1.txt’ (skipped: file exists)`

---

## 7. `rm` - Remove Files
**Description:** Deletes files or directories.  
**Examples:**
- `rm file1.txt`  
  *Example:* Deletes `/home/user/file1.txt`
- `rm -r folder/`  
  Recursively deletes a directory and its contents.  
  *Example:* Deletes `/home/user/folder/` and all its contents
- `rm -f file1.txt`  
  Force removes a file without confirmation.  
  *Example:* Deletes `/home/user/file1.txt` without prompting
- `rm -rf folder/`  
  Forcefully and recursively deletes a folder.  
  *Example:* Deletes `/home/user/folder/` and all its contents without confirmation

---

## 8. Background and Foreground Jobs
**Description:** Managing process execution.  
**Examples:**
- `command &`  
  Runs `command` in the background.  
  *Example:* `sleep 60 &` runs `sleep` in the background.
- `jobs`  
  Lists all background jobs.  
  *Example Output:* `[1] 1234`
- `fg %1`  
  Brings job number 1 to the foreground.  
  *Example:* Moves `sleep` from the background to the foreground.
- `bg %1`  
  Resumes job number 1 in the background.  
  *Example:* Continues `sleep` in the background.

---

## 9. Using `screen` for Management
**Description:** Terminal multiplexing tool.  
**Examples:**
- `screen`  
  Starts a new screen session.  
  *Example:* Creates a new session to manage multiple terminal windows.
- `screen -ls`  
  Lists all active screen sessions.  
  *Example Output:* `There is a screen on: 1234.pts-0.hostname (Detached)`
- `screen -r 1234`  
  Reattaches to the screen session with ID 1234.  
  *Example:* Reconnects to a detached session.
- `Ctrl+A` followed by `d`  
  Detaches from the current screen session.  
  *Example:* Detaches from a session, leaving it running in the background.

---

## 10. Linux Size Conversion
**Description:** Convert between different file sizes.  
**Examples:**
- `ls -lh`  
  Displays file sizes in human-readable format (e.g., KB, MB).  
  *Example Output:* `1.2K`
- `du -sh /path/to/dir`  
  Shows the size of a directory in a human-readable format.  
  *Example Output:* `1.5G`
- `stat -c %s file.txt`  
  Displays the file size in bytes.  
  *Example Output:* `123456`

---

## 11. How File Permissions Work in Linux
**Description:** Understanding file permissions.  
**Examples:**
- `ls -l`  
  Displays file permissions in a detailed list.  
  *Example Output:* `-rwxr-xr-- 1 user group 12345 Sep 1 12:00 file.txt`
- `chmod 755 file.txt`  
  Sets file permissions to `rwxr-xr-x`.  
  *Example:* Owner can read/write/execute, others can read/execute.
- `chown user:group file.txt`  
  Changes the owner and group of a file.  
  *Example:* Changes ownership to `user` and `group`.

---

## 12. File Permissions and Ownership
**Description:** Detailed permissions and ownership management.  
**Examples:**
- `chmod`  
  Modify file permissions.  
  *Example:* `chmod u+x file.txt` adds execute permission for the user.
- `chown`  
  Change file ownership.  
  *Example:* `chown user file.txt` changes the owner to `user`.
- `chgrp`  
  Change the group ownership of a file.  
  *Example:* `chgrp group file.txt` changes the group to `group`.

---

## 13. Useful Linux Commands for Data Analysis
**Description:** Commands for processing and analyzing data.  
**Examples:**
- `awk '{print $1}' file.txt`  
  Extracts and prints the first column from a file.  
  *Example Output:* Displays the first column from `file.txt`.
- `sort file.txt`  
  Sorts the contents of a file.  
  *Example Output:* Sorted lines of `file.txt`.
- `uniq file.txt`  
  Removes duplicate lines from a file.  
  *Example Output:* Unique lines from `file.txt`.
- `cut -d' ' -f1 file.txt`  
  Extracts the first field from each line using space as the delimiter.  
  *Example Output:* First field of `file.txt`.

---

## 14. Combining Commands with Pipes and Redirection
**Description:** Using pipes and redirection to combine commands.  
**Examples:**
- `command1 | command2`  
  Sends the output of `command1` as input to `command2`.  
  *Example:* `ls | grep 'file'` lists files and filters those containing 'file'.
- `command > file.txt`  
  Redirects the output of `command` to `file.txt`, overwriting it.  
  *Example:* `echo "Hello" > file.txt` writes "Hello" to `file.txt`.
- `command >> file.txt`  
  Appends the output of `command` to `file.txt`.  
  *Example:* `echo "World" >> file.txt` appends "World" to `file.txt`.

---

## 15. Automating Tasks with `while` and `for` Loops
**Description:** Automating repetitive tasks with loops.  
**Examples:**
- `while` loop  
  ```bash
  while [ condition ]; do
      command
  done

  while [ $count -lt 5 ]; do
      echo $count
      ((count++))
  done


- `for` loop  
  ```bash
  for item in list; do
    command
  done

  for file in *.txt; do
      cat "$file"
  done


## 16. Understanding Data Size Conversion

**Title:** Data Size Conversion: Bytes, Kilobytes, Megabytes, Gigabytes

**Content:**

- **Basic Units of Data:**
  - **Bit (b):** The smallest unit, 0 or 1.
  - **Byte (B):** 1 Byte = 8 bits.

- **Common Data Size Conversions:**
  - **1 Kilobyte (KB):** 1 KB = 1,024 Bytes.
  - **1 Megabyte (MB):** 1 MB = 1,024 KB.
  - **1 Gigabyte (GB):** 1 GB = 1,024 MB.
  - **1 Terabyte (TB):** 1 TB = 1,024 GB.

- **Example:**
  - A 10 MB file is equal to 10 * 1,048,576 = 10,485,760 Bytes.

---
