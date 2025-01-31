# Introduction to WSL

Windows Subsystem for Linux (WSL) is a compatibility layer for running Linux binary executables natively on Windows 10 and Windows Server 2019. It allows developers to use a Linux environment directly on a Windows machine without the overhead of a traditional virtual machine or dual-boot setup. WSL provides a seamless integration between Windows and Linux, enabling users to run Linux command-line tools, utilities, and applications alongside their Windows applications.

With WSL, you can:
- Run common command-line tools such as `grep`, `sed`, and `awk`.
- Use Linux-first tools like `bash`, `ssh`, and `git`.
- Access your Windows files from within Linux and vice versa.
- Develop and test cross-platform applications.

WSL is particularly useful for developers who work in a mixed environment and need the flexibility of both Windows and Linux. It simplifies the development workflow and enhances productivity by providing the best of both worlds.

In this guide, we will explore how to set up and use WSL, and how it can benefit your development process.


## Checking Your WSL Version

To check the version of WSL installed on your system, you can use the following command in PowerShell:

```powershell
wsl --list --verbose
```

This command will display a list of all installed Linux distributions along with their version information. The output will show whether each distribution is running on WSL 1 or WSL 2.

Alternatively, you can use:

```powershell
wsl --version
```

This command will display the version of WSL installed on your system, including the WSL 2 kernel version if applicable.

## Checking Installed Operating Systems in WSL

To check all installed operating systems in your WSL environment, you can use the following command in PowerShell:

```powershell
wsl --list --all
```

This command will display a list of all installed Linux distributions, including those that are currently stopped or not set as the default distribution.

Alternatively, you can use:

```powershell
wsl -l -v
```

This command will provide a detailed list of all installed distributions along with their version information and current state (running or stopped).

## Running a Selected Linux Distribution

To run a specific Linux distribution in WSL, you can use the following command in PowerShell:

```powershell
wsl -d <DistributionName>
```

Replace `<DistributionName>` with the name of the Linux distribution you want to run. For example, to run Ubuntu, you would use:

```powershell
wsl -d Ubuntu
```

This command will start the specified distribution and open a new terminal window with the Linux shell.

## Changing the Default Linux Distribution

To change the default Linux distribution that WSL uses when you run `wsl` without any arguments, you can use the following command in PowerShell:

```powershell
wsl --set-default <DistributionName>
```

Replace `<DistributionName>` with the name of the Linux distribution you want to set as the default. For example, to set Ubuntu as the default distribution, you would run:

```powershell
wsl --set-default Ubuntu
```

This command sets the specified distribution as the default, so it will be used whenever you run `wsl` without specifying a distribution.

## Checking Your Ubuntu Version

To check the version of Ubuntu installed in your WSL environment, you can use the following command:

```bash
lsb_release -a
```

This command will display detailed information about your Ubuntu distribution, including the version number. Alternatively, you can use:

```bash
cat /etc/os-release
```

This will provide a summary of the operating system information.

## Installing Ubuntu 22.04 in WSL

To install Ubuntu 22.04 in WSL, follow these steps:

1. **Enable WSL**:
    Open PowerShell as an administrator and run the following command to enable WSL and the Virtual Machine Platform:

    ```powershell
    wsl --install
    ```

    This command will install WSL and set WSL 2 as the default version.

2. **Install Ubuntu 22.04**:
    After enabling WSL, you can install Ubuntu 22.04 from the Microsoft Store. Open the Microsoft Store, search for "Ubuntu 22.04", and click on the "Get" button to install it.

3. **Set up Ubuntu 22.04**:
    Once the installation is complete, launch Ubuntu 22.04 from the Start menu. The first time you run it, you will be prompted to create a new user account and set a password.

4. **Verify the Installation**:
    To verify that Ubuntu 22.04 is installed correctly, you can check the version by running the following command in the Ubuntu terminal:

    ```bash
    lsb_release -a
    ```

    This command will display detailed information about your Ubuntu distribution, including the version number.

By following these steps, you will have Ubuntu 22.04 installed and running in your WSL environment, ready for development and testing.


## issues

- if linex command not working run the following command 

    export PATH="/usr/bin:$PATH"