# Lab-11: Vim Text Editor

## Objective

**Practice installing and verifying Vim, creating, editing, saving, and navigating text files using Vim, including essential editing commands and configuring Vim as the default editor.**

---

## Steps

#### Step 1: Install the Vim

**Description:** Install the Vim.

**Command:**

```bash
sudo apt install vim
```

**Expected Output:**

```text
[sudo] password for umer:
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following package was automatically installed and is no longer required:
  libfwupd2
Use 'sudo apt autoremove' to remove it.
The following additional packages will be installed:
  vim-runtime
Suggested packages:
  ctags vim-doc vim-scripts
The following NEW packages will be installed:
  vim vim-runtime
0 upgraded, 2 newly installed, 0 to remove and 68 not upgraded.
Need to get 9,158 kB of archives.
After this operation, 41.7 MB of additional disk space will be used.
Do you want to continue? [Y/n] y
Get:1 http://hk.archive.ubuntu.com/ubuntu noble-updates/main amd64 vim-runtime all 2:9.1.0016-1ubuntu7.20 [7,273 kB]
Get:2 http://hk.archive.ubuntu.com/ubuntu noble-updates/main amd64 vim amd64 2:9.1.0016-1ubuntu7.20 [1,884 kB]
Fetched 9,158 kB in 9min 21s (16.3 kB/s)
Selecting previously unselected package vim-runtime.
(Reading database ... 199861 files and directories currently installed.)
Preparing to unpack .../vim-runtime_2%3a9.1.0016-1ubuntu7.20_all.deb ...
Adding 'diversion of /usr/share/vim/vim91/doc/help.txt to /usr/share/vim/vim91/doc/help.txt.vim-tiny by vim-runtime'
```

**Screenshot:**
![](../05-Attachments/01-labs-attachments/259.png)

---

#### Step 2: Verify the Vim Installation

**Description:** Display the installed Vim version.

**Command:**

```bash
vim --version
```

**Expected Output:**

```text
VIM - Vi IMproved 9.1 (2024 Jan 02, compiled Aug 24 2026 22:13:04)
Included patches: 1-16, 647, 678, 697
Modified by team+vim@tracker.debian.org
Compiled by team+vim@tracker.debian.org
```

**Screenshot:**
![](../05-Attachments/01-labs-attachments/260.png)

---

#### Step 3: Create and Open a File Using Vim

**Description:** Create and open `file.txt` in Vim.

**Command:**

```bash
vim file.txt
```

**Screenshot:**
![](../05-Attachments/01-labs-attachments/261.png)

> [!NOTE] 
> **If the Vim Setup screen appears, press `2` to open Vim.**

---

#### Step 4: Enter Insert Mode

**Description:** Enter Insert Mode to type text into the file.

**Command:**

```vim
i
```

**Screenshot:**
![](../05-Attachments/01-labs-attachments/262.png)


> [!NOTE] 
> **In Vim Editor, pressing `i` switches the editor from Normal Mode to Insert Mode, and the editor displays `INSERT` at the bottom of the screen.**

---

#### Step 5: Add Text to the File

**Description:** Enter the following text into the file.

**Text:**

```text
This is the line 1.
This is the line 2.
This is the line 3.
This is the line 4.
This is the line 5.
```

**Screenshot:**
![](../05-Attachments/01-labs-attachments/263.png)

---

#### Step 6: Return to Normal Mode

**Description:** Exit Insert Mode and return to Normal Mode.

**Command:**

```vim
Esc
```

**Screenshot:**
![](../05-Attachments/01-labs-attachments/264.png)

---

#### Step 7: Save and Exit Vim

**Description:** Save the file and exit Vim.

**Command:**

```vim
:wq
```

**Screenshot:**
![](../05-Attachments/01-labs-attachments/265.png)


> [!NOTE] 
> **Press `Esc` to enter Normal mode, then press `Shift + ZZ` to save the file and exit Vim.**

---

#### Step 8: Verify the File Contents

**Description:** Display the contents of `file.txt`.

**Command:**

```bash
cat file.txt
```

**Expected Output:**

```text
This is the line 1.
This is the line 2.
This is the line 3.
This is the line 4.
This is the line 5.
```

**Screenshot:**
![](../05-Attachments/01-labs-attachments/266.png)

---

#### Step 9: Reopen the File in Vim

**Description:** Open the existing `file.txt` in Vim.

**Command:**

```bash 
vim file.txt
```

**Screenshot:**
![](../05-Attachments/01-labs-attachments/267.png)

---

#### Step 10: Display Line Numbers

**Description:** Display line numbers.

**Command:**

```vim
:set number
```

**Screenshot:**
![](../05-Attachments/01-labs-attachments/268.png)


> [!NOTE] 
> **Press `Esc` to enter Normal mode, type `:set number`, and press `Enter` to display line numbers.**

---

#### Step 11: Navigate to a Specific Line

**Description:** Move the cursor to line 2.

**Command:**

```vim
:2 
```

**Screenshot:**
![](../05-Attachments/01-labs-attachments/269.png)


> [!NOTE] 
> **Press `Esc` to enter Normal mode, type `:2`, and press `Enter` to move the cursor to line 2.**

---

#### Step 12: Navigate to the First Line

**Description:** Move the cursor to the first line of the file.

**Command:**

```vim
gg
```

**Screenshot:**
![](../05-Attachments/01-labs-attachments/270.png)


> [!NOTE] 
> **Press `Esc` to enter Normal mode and press `gg` to move the cursor to the first line of the file.**

---

#### Step 13: Navigate to the Last Line

**Description:** Move the cursor to the last line of the file.

**Command:**

```vim
Shift + G
```

**Screenshot:**
![](../05-Attachments/01-labs-attachments/271.png)


> [!NOTE] 
> **Press `Esc` to enter Normal mode and press `Shift + G` to move the cursor to the last line of the file.**

---

#### Step 14: Navigate to the Start of the Line

**Description:** Move the cursor to the beginning of the current line.

**Command:**

```vim
0
```

**Screenshot:**
![](../05-Attachments/01-labs-attachments/272.png)


> [!NOTE] 
> **Press `Esc` to enter Normal mode and press `0` to move the cursor to the beginning of the current line.**

---

#### Step 15: Navigate to the End of the Line

**Description:** Move the cursor to the end of the current line.

**Command:**

```vim
$
```

**Screenshot:**
![](../05-Attachments/01-labs-attachments/273.png)


> [!NOTE] 
> **Press `Esc` to enter Normal mode and press `$` to move the cursor to the end of the current line.**

---

#### Step 16: Add a New Line Below the Current Line

**Description:** Create a new line below the current line and Enter Insert Mode.

**Command:**

```vim
o
```

**Screenshot:**
![](../05-Attachments/01-labs-attachments/274.png)


> [!NOTE] 
> **Press `Esc` to enter Normal mode and press `o` to  Create a new line below the current line and Enter Insert Mode.**

---

#### Step 17: Add a New Line Above the Current Line

**Description:** Create a new line above the current line and Enter Insert Mode.

**Command:**

```vim
Shift + O
```

**Screenshot:**
![](../05-Attachments/01-labs-attachments/275.png)


> [!NOTE] 
> **Press `Esc` to enter Normal mode and press `Shift + O` to  Create a new line above the current line and Enter Insert Mode.**

---

#### Step 18: Delete the Current Line

**Description:** Delete the current line.

**Command:**

```vim
dd
```

**Screenshot:**
![](../05-Attachments/01-labs-attachments/276.png)


> [!NOTE] 
> **Press `Esc` to enter Normal mode and press `dd` to Delete the current line.**

---

#### Step 19: Copy the Current Line

**Description:** Copy the current line.

**Command:**

```vim
yy
```

**Screenshot:**
![](../05-Attachments/01-labs-attachments/277.png)


> [!NOTE] 
> **Press `Esc` to enter Normal mode and press `yy` to Copy the current line.**

---

#### Step 20: Paste the Copied Line

**Description:** Paste the copied line below the current line.

**Command:**

```vim
p
```

**Screenshot:**
![](../05-Attachments/01-labs-attachments/278.png)


> [!NOTE] 
> **Press `Esc` to enter Normal mode and press `p` to Paste the copied line below the current line.**

---

#### Step 21: Undo the Last Action

**Description:** Undo the last change.

**Command:**

```vim
u
```

**Screenshot:**
![](../05-Attachments/01-labs-attachments/279.png)


> [!NOTE] 
> **Press `Esc` to enter Normal mode and press `u` to Undo the last change.**

---

#### Step 22: Search for Text

**Description:** Search for the text `line 3` in the file.

**Command:**

```vim
/line 3
```

**Navigation:**

1. Press `Esc` to enter Normal mode.
2. Type `/line 3` to search for the text `line 3`.
3. Press `Enter` to move the cursor to the first character of the first match.
4. Press `n` to go to the next match.
5. Press `Shift + N` to go to the previous match.

**Screenshot:**
![](../05-Attachments/01-labs-attachments/280.png)


> [!NOTE] 
> **Press `Esc` to enter Normal mode, type `/line 3`, and press `Enter` to move the cursor to the first character of the first matching occurrence.**

---
#### Step 23: Move the Cursor to a Specific Line and Column

**Description:** Move the cursor to line 6, column 4.

**Command:**

```vim
:call cursor(6,4)
```

**Screenshot:**
![](../05-Attachments/01-labs-attachments/281.png)


> [!NOTE] 
> **Press `Esc` to enter Normal mode, type `:call cursor(6,4)`, and press `Enter` to move the cursor to line 6, column 4.**

---
#### Step 24: Exit Vim Without Saving Changes

**Description:** Exit Vim without saving the changes made to the file.

**Command:**

```vim
:q!
```

**Screenshot:**
![](../05-Attachments/01-labs-attachments/282.png)


> [!NOTE] 
> **Press `Esc` to enter Normal mode, then press `Shift + ZQ` to exit Vim without saving changes.**

---

#### Step 25: Verify the File Contents

**Description:** Display the contents of `file.txt` to verify that the unsaved changes were discarded and the original five lines remain unchanged.

**Command:**

```bash
cat file.txt
```

**Expected Output:**

```text
This is the line 1.
This is the line 2.
This is the line 3.
This is the line 4.
This is the line 5.
```

**Screenshot:**
![](../05-Attachments/01-labs-attachments/283.png)

---

#### Step 26: Find Bash Configuration Files

**Description:** Find regular files containing `bash` in their names under `/etc`.

**Command:**

```bash
sudo find /etc -type f -name "*bash*"
```

**Expected Output:**

```text
/etc/bash.bashrc
/etc/skel/.bashrc
```

**Screenshot:**


---

#### Step 28: Configure Vim as the Default Editor

**Description:** Open the system-wide Bash configuration file with administrator privileges.

**Command:**

```bash
sudo vim /etc/bash.bashrc
```

**Screenshot:**

Press `i` to Enter Insert mode into the file and add the following lines at the end of the file:

```bash
export EDITOR=vim
export VISUAL=vim
```

**Screenshot:**


> [!NOTE] 
> **Press `Esc` to enter Normal mode, then press `:wq` to save the file and exit Vim.**

---

#### Step 29: Reload the Bash Configuration

**Description:** Reload the system-wide Bash configuration in the current Bash session.

**Command:**

```bash
source /etc/bash.bashrc
```

**Screenshot:**


---

#### Step 30: Verify the Default Editor

**Description:** Display the value of the `EDITOR` environment variable.

**Command:**

```bash
echo $EDITOR
```

**Expected Output:**

```text
vim
```

**Screenshot:**

**Description:** Display the value of the `VISUAL` environment variable.

**Command:**

```bash
echo $VISUAL
```

**Expected Output:**

```text
vim
```

**Screenshot:**

---

## Conclusion

**Learned how to install and verify Vim, create, edit, save, and navigate text files, and practice essential editing commands. Also searched for text and configured Vim as the default editor.**
