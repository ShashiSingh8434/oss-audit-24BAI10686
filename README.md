# OSS-Audit-24BAI10686

> A capstone project for the Open Source Software course, involving a detailed audit of the Apache HTTP Server, supported by Linux-based shell scripting assignments.

---

## Student Information

| Field                  | Details              |
|------------------------|----------------------|
| **Student Name**       | Shashi Singh         |
| **Registration Number**| 24BAI10686           |
| **Course**             | Open Source Software |

---

## Project Overview

The objective of this research effort is to provide a comprehensive analysis of the Apache HTTP Server, one of the most used open system web servers in the world, and it will discuss both the theory behind and the practical use of such a product.

The analysis will include:

- How Apache HTTP Server started, developed, and has developed over the years
- What the Apache License 2.0 is and what it allows and requires
- The open-source ecosystem and community that supports Apache HTTP Server and continues to improve it
- How Apache compares to proprietary web server products
- A hands-on implementation of five Linux Bash scripts that demonstrate some of the major concepts associated with systems administration.

To connect the theoretical aspects of this research with practical application, the hands-on portion (the scripting portions) of this project will focus on using Linux command-line utilities, working with files, reviewing processes, and performing basic auditing tasks in a practical setting. This will lead to a better and more practical understanding of how open source systems operate.

---

## Tech Stack

| Component            | Details                                                          |
|----------------------|------------------------------------------------------------------|
| **Operating System** | Kali Linux / Ubuntu (Linux-based)                                |
| **Shell**            | Bash (`/bin/bash`)                                               |
| **Web Server**       | Apache HTTP Server (`apache2`)                                   |
| **Package Manager**  | `apt` (Advanced Package Tool)                                    |
| **Core Utilities**   | `uname`, `whoami`, `dpkg`, `du`, `grep`, `awk`, `date`, `uptime` |

---

## Project Structure

``` open-source-audit-apache/

│

├── Script1.sh                 # System Identity Report

├── Script2.sh                 # Check FOSS packages

├── Script3.sh                 # Check disk and permissions

├── Script4.sh                 # Analyze log files

├── Script5.sh                 # Generate Open Source Manifesto

├── Screenshots                # Folder for output screenshots

├── The Open Source Audit      # Project report

│

└── README.md                  # Documentation, for the project

```
---

## Setup Instructions

### Prerequisites

Ensure you are running a Debian/Ubuntu-based Linux distribution (Kali Linux or Ubuntu recommended).

### Step 1 — Update Package Lists

```bash
sudo apt update
```

### Step 2 — Install Apache HTTP Server

```bash
sudo apt install apache2 -y
```

### Step 3 — Verify Installation

```bash
apache2 -v
```

### Step 4 — Make Scripts Executable

```bash
chmod +x Script1.sh Script2.sh Script3.sh Script4.sh Script5.sh
```

---

## How to Run the Scripts

| Script       | Command                                        |
|--------------|------------------------------------------------|
| `Script1.sh` | `./Script1.sh`                                 |
| `Script2.sh` | `./Script2.sh`                                 |
| `Script3.sh` | `./Script3.sh`                                 |
| `Script4.sh` | `./Script4.sh /var/log/apache2/error.log error`|
| `Script5.sh` | `./Script5.sh`                                 |

> **Note:** The script4.sh file needs two things to work. It needs to know where to find a log file. What word you want it to look for. If you do not tell it what word to look for it will look for the word error, by default.

---

## Script Descriptions

| Script       | Title                        | Description                                                                                                  |

|--------------|------------------------------|--------------------------------------------------------------------------------------------------------------|

| `Script1.sh` | System Identity Report       | This script shows system information. It includes the kernel version, the user who is logged in the name of the operating system how long the system has been running and the current date and time. |

| `Script2.sh` | FOSS Package Inspector       | The `Script2.sh` script checks if `apache2` is installed on the system using `dpkg`. It then shows details about the package. Uses a `case` statement to print a note about what the package is all about. |

| `Script3.sh` | Disk and Permission Auditor  | The `Script3.sh` script goes through a list of system directories that we have already chosen. For each directory it reports what permissions it has, who owns it and how disk space it is using. It also checks if the directory for Apache configuration is there. |

| `Script4.sh` | Log File Analyzer            | The `Script4.sh` script asks for a log file and a keyword. It then counts how times the keyword appears in the log file, line by line using a `while` loop. Finally it shows the five lines where the keyword was found. |

`Script5.sh` | Open Source Manifesto Generator | The `Script5.sh` script asks the user for three things. It collects some information about the system. Then generates a special open-source manifesto just for the user. This manifesto is saved in a file. The `Script5.sh` script is, about creating this personalized manifesto. |

---

## Output Explanation

- **Script1.sh** — Prints a formatted system audit panel with distribution, kernel, user, home directory, uptime, date, and GPL license note.
- **Script2.sh** — Confirms whether Apache is installed and outputs version/package details. The `case` block prints a contextual philosophy note.
- **Script3.sh** — Produces a directory audit table showing permissions, owner, group, and size for `/etc`, `/var/log`, `/home`, `/usr/bin`, `/tmp`, and the Apache config directory.
- **Script4.sh** — Outputs a log analysis report: file name, keyword searched, total occurrence count, and the last five matching log lines.
- **Script5.sh** — Generates a `manifesto_<username>.txt` file containing a personalised open-source manifesto based on user-provided inputs, then displays it on screen.

---

## Concepts Used

The set of five shell scripts shows how to use core Linux and shell scripting concepts.

- **Variables** are used everywhere. They can be defined by the user like when you set a name or generated by the system, such as `$(whoami)`. $(Uname -r)`. You use **Variables** to store and use values.

- The scripts handle **User Input**. They use `read -p` to get input from you and then respond based on what you say. **User Input** helps the scripts make decisions.

- **Conditional Statements** like `if-else` are used to check things. For example they check if a file exists or if a package is installed. You need **Conditional Statements** to make choices.

- The scripts use **Case Statements** to handle conditions at once. This is really helpful when dealing with package options. **Case Statements** make it easy to manage choices.

- **Loops** are used in ways. There are `for` loops that go through lists and `while` loops that go through files line by line. You use **Loops** to repeat tasks.

- The scripts support **Command-line Arguments**. They use things like `$1` and `$2`. If you do not give any arguments they have default values. **Command-line Arguments** let you customize the script.

- **File Handling** includes reading files. The scripts use `IFS= read -r` to read files. They also write output with redirection (`>`). You need **File Handling** to work with files.

- The scripts use **Text Processing Tools** like `grep` `awk` `cut` `tail` and `tr`. These tools help filter, get and change data. **Text Processing Tools** are useful, for working with text.

- They use **System Commands** like `du` `-ld` `dpkg` `date` `uptime` and `uname`. These commands help interact with the system and get information. **System Commands** give you system details.

- The scripts use **Exit Codes** like `exit 1`. They handle errors. Stop the script in a controlled way. **Exit Codes** help manage errors.

- They also have a *Retry Mechanism**. It checks again after a delay using `sleep`. This makes the scripts more reliable. The **Retry Mechanism** helps fix problems.

---

## Notes

- All scripts are written for Linux environments only. They will not work on Windows or macOS without a layer.

- You need to make scripts executable before running them. Use `chmod +x <script>` to do this.

- `Script4.sh` needs a log file as its argument. You can use `/var/log/syslog` on Ubuntu or `/var/log/kern.log` on Kali Linux for testing.

- `Script3.sh` reads system directories. If size values look incomplete run it with `sudo` because it may need permissions.

- `Script5.sh` creates a manifesto file in your current directory. The file is named `manifesto_<username>.txt`.

---

## Conclusion

In this project, the Apache HTTP Server — one of the foundational elements of an open web — will be used as an example to demonstrate a working knowledge of what open-source means or represents.

The scripting part of the assignment is meant to build on basic Linux administration skills and represent some of the values that are at the heart of an open-source culture — such as being transparent, working together, and being free to look at and change the code.

The theoretical analysis and practical scripting components together provide a comprehensive study of real-world open-source software. 

---

*This work is being submitted as an element of the Open Source Software course assignment.*