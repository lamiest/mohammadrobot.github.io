# Introduction to ROS with Linux

Robot Operating System (ROS) is an open-source framework that helps researchers and developers build and reuse code between robotics applications. It provides services designed for a heterogeneous computer cluster such as hardware abstraction, low-level device control, implementation of commonly-used functionality, message-passing between processes, and package management.

## Why Use ROS with Linux?

Linux is the most popular operating system for ROS development due to its stability, flexibility, and extensive support for open-source software. ROS is primarily developed for Ubuntu, a popular Linux distribution, making it the preferred choice for many robotics projects.

### Key Features of ROS

- **Modularity**: ROS is designed to be modular, allowing developers to create reusable code.
- **Tools and Libraries**: ROS provides a wide range of tools and libraries to simplify the development process.
- **Community Support**: A large and active community contributes to the continuous improvement of ROS.

### Getting Started

To get started with ROS on Linux, you will need to:

1. **Install Ubuntu**: ROS is best supported on Ubuntu. You can download and install the latest version from the [official Ubuntu website](https://ubuntu.com/download).
2. **Install ROS**: Follow the installation instructions on the [ROS Wiki](http://wiki.ros.org/ROS/Installation) to set up ROS on your Ubuntu system.
3. **Learn ROS Basics**: Familiarize yourself with the basic concepts and tools of ROS by following tutorials available on the [ROS Wiki](http://wiki.ros.org/ROS/Tutorials).

By leveraging the power of ROS and Linux, you can accelerate your robotics development and create robust, scalable applications.
### Basic Linux Commands for ROS Development

When working with ROS on Linux, it's essential to be familiar with some basic Linux commands. Here are a few commands that will help you navigate and manage your ROS environment:

- **Navigating Directories**:
    - `cd [directory]`: Change the current directory to the specified directory.
    - `ls`: List the contents of the current directory.
    - `pwd`: Print the current working directory.

- **File Management**:
    - `cp [source] [destination]`: Copy files or directories.
    - `mv [source] [destination]`: Move or rename files or directories.
    - `rm [file]`: Remove files.
    - `mkdir [directory]`: Create a new directory.

- **System Updates and Package Management**:
    - `sudo apt update`: Update the package list.
    - `sudo apt upgrade`: Upgrade all installed packages to their latest versions.
    - `sudo apt install [package]`: Install a new package.

- **ROS-Specific Commands**:
    - `source /opt/ros/[distro]/setup.bash`: Source the ROS setup file to configure your environment.
    - `roscore`: Start the ROS master node.
    - `rosrun [package] [executable]`: Run a ROS node from a specific package.
    - `roslaunch [package] [launchfile]`: Launch a ROS launch file.

By mastering these basic Linux commands, you can efficiently manage your ROS projects and streamline your development workflow.
### Updating Your `.bashrc` File for ROS

To ensure that your ROS environment is set up correctly every time you open a new terminal, you need to update your `.bashrc` file. The `.bashrc` file is a script that runs whenever you start a new terminal session in Linux.

1. **Open the `.bashrc` file**:
    ```sh
    nano ~/.bashrc
    ```

2. **Add the ROS setup script**: Scroll to the bottom of the file and add the following line to source the ROS setup script:
    ```sh
    source /opt/ros/[distro]/setup.bash
    ```
    Replace `[distro]` with the name of your ROS distribution (e.g., `noetic`, `melodic`).

3. **Save and close the file**: Press `CTRL + X`, then `Y`, and `Enter` to save and exit.

4. **Apply the changes**: Run the following command to apply the changes made to the `.bashrc` file:
    ```sh
    source ~/.bashrc
    ```

By updating your `.bashrc` file, you ensure that your ROS environment is configured correctly every time you open a new terminal, making it easier to work on your ROS projects.

### Checking Linux Hardware Specifications

When working with ROS on Linux, it's important to know the hardware specifications of your system. Here are some commands to check various hardware details:

- **CPU Information**:
    ```sh
    lscpu
    ```
    This command displays detailed information about the CPU architecture.

- **Memory Information**:
    ```sh
    free -h
    ```
    This command shows the total, used, and free memory in a human-readable format.

- **Disk Usage**:
    ```sh
    df -h
    ```
    This command provides an overview of the disk usage for all mounted filesystems.

- **Detailed Hardware Information**:
    ```sh
    lshw
    ```
    This command lists detailed information about all hardware components. You may need to run it with `sudo` for complete details:
    ```sh
    sudo lshw
    ```

- **Graphics Card Information**:
    ```sh
    lspci | grep -i vga
    ```
    This command filters the PCI devices to show information about the graphics card.

By using these commands, you can gather comprehensive information about your Linux system's hardware, which can be useful for optimizing your ROS development environment.

