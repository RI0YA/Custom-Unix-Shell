MyShell is a custom Unix-based shell developed in C, designed to bridge the gap between a standard command-line interface and a dedicated forensic monitoring tool. While traditional shells (like Bash or Zsh) focus primarily on command execution, MyShell is engineered with a Security-First philosophy. It features real-time file integrity monitoring, automated audit logging, and a proactive intelligence layer that recognizes user behavior patterns to optimize the development workflow.

### Key Technical Features
Forensic Watch Engine (cmd_watch.c): A persistent monitoring module that tracks file metadata, including Inode values and permission shifts. It allows users to detect unauthorized modifications in real-time, even if filenames are obfuscated.

Proactive Intelligence Module (cmd_suggest.c): An integrated pattern-recognition engine that analyzes the command history. If a user repeatedly enters complex, multi-word commands (5+ words), the shell identifies the "typing fatigue" and automatically suggests efficient Alias shortcuts.
* Tamper-Proof Audit Logging: Every interaction within the shell is captured in shell_audit.log with high-resolution timestamps and User IDs (UIDs). The shell includes a Security Sentinel (--secure) that monitors the integrity of the audit log itself.
* Network Diagnostic Layer (cmd_net.c): Provides deep-dive network visibility by mapping active socket connections directly to their owning Process IDs (PIDs) and users, a critical feature for hunting malicious background processes.
* Resilient Signal Handling: Custom implementation of SIGINT (Ctrl+C) ensures that the parent shell remains active during monitoring tasks, preventing session termination during intensive forensic analysis.

### Technical Stack
Language: C (POSIX compliant)
Build System: Modular Makefile (Incremental Compilation)
Key Libraries: <sys/stat.h>, <signal.h> (Interrupts), <unistd.h> (Process Control), <dirent.h> (Filesystem Traversal).

### Contributors
This project was developed as part of the CDAC Hyderabad CP-ASSD program by:

Riya Gupta 
Vamsi
Naisha Dekate
