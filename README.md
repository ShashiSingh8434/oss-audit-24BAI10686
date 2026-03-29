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

This project provides a detailed audit of the **Apache HTTP Server**, one of the most widely used open-source web servers across the globe. It explores both the theoretical background and practical aspects of working with such a system.

The audit includes:

- The origin, development, and evolution of the Apache HTTP Server over time  
- Its licensing model under the Apache License 2.0, along with what it allows and implies  
- The open-source ecosystem and community that support and maintain it  
- A comparison between Apache and proprietary web server solutions  
- A hands-on implementation using five Linux-based Bash scripts that demonstrate key system administration concepts  

To bridge theory with practice, the scripting part of the project focuses on applying Linux command-line utilities, working with files, inspecting processes, and performing basic system auditing tasks in a real-world environment. This approach helps in building a clearer and more practical understanding of open-source system operations.

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

```
open-source-audit-apache/
│
├── Script1.sh                 # System Identity Report
├── Script2.sh                 # FOSS Package Inspector
├── Script3.sh                 # Disk and Permission Auditor
├── Script4.sh                 # Log File Analyzer
├── Script5.sh                 # Open Source Manifesto Generator
| 
├── Screenshots                # Output Screenshots folder
├── The Open Source Audit      # Report of the Project
│
└── README.md                  # Project documentation
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

> **Note:** `script4.sh` requires two arguments — the path to a log file and a keyword to search for. The keyword defaults to `error` if not provided.

---

## Script Descriptions

| Script       | Title                        | Description                                                                                                  |
|--------------|------------------------------|--------------------------------------------------------------------------------------------------------------|
| `Script1.sh` | System Identity Report       | Displays key system information including kernel version, logged-in user, distro name, uptime, and date/time. |
| `Script2.sh` | FOSS Package Inspector       | Checks whether `apache2` is installed using `dpkg`, displays package details, and uses a `case` statement to print a philosophy note about the package. |
| `Script3.sh` | Disk and Permission Auditor  | Iterates over a predefined list of system directories, reporting their permissions, ownership, and disk usage. Also checks for the Apache configuration directory. |
| `Script4.sh` | Log File Analyzer            | Accepts a log file path and keyword as arguments, counts keyword occurrences line by line using a `while` loop, and displays the last five matching lines. |
| `Script5.sh` | Open Source Manifesto Generator | Prompts the user for three inputs, collects system metadata, and generates a personalized open-source manifesto saved to a `.txt` file. |

---

## Output Explanation

- **Script1.sh** — Prints a formatted system audit panel with distribution, kernel, user, home directory, uptime, date, and GPL license note.
- **Script2.sh** — Confirms whether Apache is installed and outputs version/package details. The `case` block prints a contextual philosophy note.
- **Script3.sh** — Produces a directory audit table showing permissions, owner, group, and size for `/etc`, `/var/log`, `/home`, `/usr/bin`, `/tmp`, and the Apache config directory.
- **Script4.sh** — Outputs a log analysis report: file name, keyword searched, total occurrence count, and the last five matching log lines.
- **Script5.sh** — Generates a `manifesto_<username>.txt` file containing a personalised open-source manifesto based on user-provided inputs, then displays it on screen.

---

## Concepts Used

The set of five shell scripts demonstrates a range of core Linux and shell scripting concepts in a practical and hands-on manner:

- **Variables** are used throughout, including both user-defined values and system-generated ones such as `$(whoami)` and `$(uname -r)`.  
- **User Input** is handled interactively using `read -p`, allowing the scripts to respond dynamically based on user input.  
- **Conditional Statements** (`if-else`) are applied to evaluate conditions like file existence or checking if a package is installed.  
- **Case Statements** are used to manage multiple conditions efficiently, particularly when dealing with different package options.  
- **Loops** are utilized effectively, with `for` loops iterating over arrays and `while` loops processing file content line by line.  
- **Command-line Arguments** are supported using positional parameters like `$1` and `$2`, with fallback default values when arguments are not provided.  
- **File Handling (I/O)** includes reading files safely using `IFS= read -r` and writing output using redirection (`>`).  
- **Text Processing Tools** such as `grep`, `awk`, `cut`, `tail`, and `tr` are used for filtering, extracting, and transforming data.  
- **System Commands** like `du`, `ls -ld`, `dpkg`, `date`, `uptime`, and `uname` are integrated to interact with and retrieve system-level information.  
- **Exit Codes** (`exit 1`) are implemented for proper error handling and controlled termination of scripts.  
- **Retry Mechanism** is introduced by rechecking conditions after a delay using `sleep`, improving script reliability.  

---

## Notes

- All scripts are written for **Linux environments only**. They will not run natively on Windows or macOS without a compatibility layer.
- Scripts must be granted execute permission before running (`chmod +x <script>`).
- `Script4.sh` requires a valid, readable log file as its first argument. An appropriate test file is `/var/log/syslog` on Ubuntu or `/var/log/kern.log` on Kali Linux.
- `Script3.sh` reads system directories that may require elevated permissions for accurate size reporting. Run with `sudo` if size values appear incomplete.
- The manifesto file generated by `Script5.sh` is saved in the current working directory as `manifesto_<username>.txt`.

---

## Conclusion

This project demonstrates a practical understanding of open-source principles through the lens of the Apache HTTP Server — a cornerstone of the open web. The scripting assignments reinforce foundational Linux administration skills and reflect the values central to open-source culture: transparency, collaboration, and freedom to inspect and modify software. Together, the theoretical audit and practical scripts form a complete study of open-source software in a real-world context.

---

*Submitted as part of the Open Source Software course assignment.*
