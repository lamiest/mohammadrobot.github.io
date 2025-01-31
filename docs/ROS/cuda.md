# Introduction to CUDA

CUDA (Compute Unified Device Architecture) is a parallel computing platform and application programming interface (API) model created by NVIDIA. It allows developers to use NVIDIA GPUs for general purpose processing (an approach known as GPGPU, General-Purpose computing on Graphics Processing Units). CUDA provides a significant performance boost by leveraging the parallel processing power of GPUs, making it ideal for compute-intensive tasks such as scientific simulations, machine learning, and image processing.

With CUDA, developers can write programs in C, C++, and Fortran, and execute them on the GPU, taking advantage of its massive parallelism. The CUDA toolkit includes libraries, debugging and optimization tools, a compiler, and a runtime library to help developers create high-performance applications.

In summary, CUDA is a powerful tool for accelerating computational tasks by harnessing the power of NVIDIA GPUs, enabling faster and more efficient processing for a wide range of applications.


### Checking NVIDIA Driver Version

If you are using an NVIDIA graphics card, it's important to ensure that the correct driver is installed for optimal performance. Here are the steps to check the NVIDIA driver version on your Linux system:

1. **Check the NVIDIA Driver Version**:
    ```sh
    nvidia-smi
    ```
    This command displays the NVIDIA System Management Interface, which includes information about the installed driver version and the GPU.

2. **Check the Installed NVIDIA Packages**:
    ```sh
    dpkg -l | grep -i nvidia
    ```
    This command lists all installed NVIDIA packages, which can help you verify the driver and related software versions.

By using these commands, you can easily check the NVIDIA driver version and ensure that your system is configured correctly for ROS development with an NVIDIA GPU.

### Installing CUDA on WSL for Ubuntu 22.04

To install CUDA on Windows Subsystem for Linux (WSL) with Ubuntu 22.04, follow these steps:

1. **Install WSL and Ubuntu 22.04**:
    Ensure that WSL and Ubuntu 22.04 are installed on your Windows system. You can install WSL and set up Ubuntu 22.04 from the Microsoft Store.

2. **Update the Package List**:
    Open your WSL terminal and update the package list:
    ```sh
    sudo apt update
    sudo apt upgrade
    ```

3. **Install NVIDIA Driver on Windows**:
    Download and install the latest NVIDIA driver for your GPU from the [NVIDIA website](https://www.nvidia.com/Download/index.aspx).

4. **Install CUDA Toolkit**:
    Add the CUDA repository and install the CUDA toolkit:
    ```sh
    wget https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2204/x86_64/cuda-ubuntu2204.pin
    sudo mv cuda-ubuntu2204.pin /etc/apt/preferences.d/cuda-repository-pin-600
    sudo apt-key adv --fetch-keys https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2204/x86_64/7fa2af80.pub
    sudo add-apt-repository "deb https://developer.download.nvidia.com/compute/cuda/repos/ubuntu2204/x86_64/ /"
    sudo apt update
    sudo apt install -y cuda
    ```

5. **Set Up Environment Variables**:
    Add CUDA to your PATH by editing the `.bashrc` file:
    ```sh
    echo 'export PATH=/usr/local/cuda-12.8/bin:$PATH' >> ~/.bashrc
    echo 'export LD_LIBRARY_PATH=/usr/local/cuda-12.8/lib64:$LD_LIBRARY_PATH' >> ~/.bashrc
    source ~/.bashrc
    ```

6. **Verify the Installation**:
    Check the CUDA version to verify the installation:
    ```sh
    nvcc --version
    ```

By following these steps, you can install CUDA on WSL for Ubuntu 22.04 and start developing CUDA applications on your system.


### Testing CUDA Installation

After installing CUDA, it's important to verify that it is working correctly on your system. Here are the steps to test your CUDA installation:

1. **Compile and Run the Device Query Example**:
    The CUDA toolkit includes several sample programs. One of them is the deviceQuery program, which provides information about the CUDA-capable devices present in the system. To compile and run this example, follow these steps:
    ```sh
    cd /usr/local/cuda-12.8/extras/demo_suite/
    sudo make
    ./deviceQuery
    ```
    If the CUDA installation is correct, this program will display information about your GPU.

2. **Compile and Run the Bandwidth Test Example**:
    Another useful sample program is the bandwidthTest, which measures the memory bandwidth between the host and the device. To compile and run this example, use the following commands:
    ```sh
    cd /usr/local/cuda/extras/demo_suite/
    sudo make
    ./bandwidthTest
    ```
    This test will provide information about the memory transfer rates, which can help you verify the performance of your CUDA setup.

By running these sample programs, you can ensure that your CUDA installation is functioning correctly and that your system is ready for CUDA development.
