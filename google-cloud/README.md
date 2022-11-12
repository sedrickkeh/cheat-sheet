[Google Cloud Console](https://console.cloud.google.com)


# Using a GPU
0. Confirm that the system has a GPU:
    - `sudo apt-get install pciutils`
    - To check: `lspci | grep -i nvidia`
    - To check Linux system: `uname -m && cat /etc/*release`
1. Install important packages (such as `wget` and `gcc`)
    - `sudo apt update`
    - `sudo apt-get install wget`
    - `sudo apt install zip`
    - `sudo apt install build-essential`
    - `sudo apt-get install manpages-dev`
    - `sudo apt-get install software-properties-common`
    - To check: `gcc --version`
2. Install some more packages
    - `sudo apt-get install linux-headers-$(uname -r)`
3. Download the NVIDIA CUDA toolkit (https://developer.nvidia.com/cuda-downloads)
    - Select the correct settings and follow the instructions there.
    - Probably the [Debian](https://developer.nvidia.com/cuda-downloads?target_os=Linux&target_arch=x86_64&Distribution=Debian&target_version=11&target_type=deb_local) setting is the one you want.

