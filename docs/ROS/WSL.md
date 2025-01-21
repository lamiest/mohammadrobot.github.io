# Introduction to WSL

Windows Subsystem for Linux (WSL) is a compatibility layer for running Linux binary executables natively on Windows 10 and Windows Server 2019. It allows developers to use a Linux environment directly on a Windows machine without the overhead of a traditional virtual machine or dual-boot setup. WSL provides a seamless integration between Windows and Linux, enabling users to run Linux command-line tools, utilities, and applications alongside their Windows applications.

With WSL, you can:
- Run common command-line tools such as `grep`, `sed`, and `awk`.
- Use Linux-first tools like `bash`, `ssh`, and `git`.
- Access your Windows files from within Linux and vice versa.
- Develop and test cross-platform applications.

WSL is particularly useful for developers who work in a mixed environment and need the flexibility of both Windows and Linux. It simplifies the development workflow and enhances productivity by providing the best of both worlds.

In this guide, we will explore how to set up and use WSL, and how it can benefit your development process.





## issues

- if linex command not working run the following command 

    export PATH="/usr/bin:$PATH"