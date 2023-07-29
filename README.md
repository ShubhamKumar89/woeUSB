# woeUSB

WoeUSB is an open-source tool to create **Windows** USB bootable installation sticks from an ISO file or DVD on Linux systems. The program supports Windows 7, Windows 8.1, and Windows 10 ISO files and can be used via a graphical user interface or in a terminal. 

# Steps to install and use WoeUSB on Ubuntu Linux

## Method 1 -  Using PPA repository

### 1. Add WoeUSB PPA repository

```bash
sudo add-apt-repository ppa:tomtomtom/woeusb -y
```

### 2. Refresh APT Index Cache

```bash
sudo apt update -y && sudo apt upgrade -y
```

### 3. Install the WoeUSB CLI + GUI on Ubuntu 22.04 | 20.04

```bash
sudo apt install woeusb woeusb-frontend-wxgtk -y
```

### Check Version

```bash
woeusb --version
```

### Error 

If you get the following error:

```bash
Reading package lists... Done
Building dependency tree
Reading state information... Done
Some packages could not be installed. This may mean that you have
requested an impossible situation or if you are using the unstable
distribution that some required packages have not yet been created
or been moved out of Incoming.
The following information may help to resolve the situation:

The following packages have unmet dependencies:
woeusb : Depends: libwxgtk3.0-0v5 (>= 3.0.4+dfsg) but it is not installable
```

Then, first, we have to install the `libwxgtk3.0` manually. Here is the command to do that:

```bash
wget http://mirrors.kernel.org/ubuntu/pool/universe/w/wxwidgets3.0/libwxgtk3.0-0v5_3.0.4+dfsg-3_amd64.deb
```

Now, install it:

```bash
sudo dpkg -i filename
# Replace the filename with the package you downloaded above, e.g.
# sudo dpkg -i libwxgtk*_amd64.deb
```

Finally, install `WoeUSB`, this time you will not get any error at all.

```bash
sudo apt update
sudo apt install woeusb woeusb-frontend-wxgtk -y
```

## Method 2 -  Using the bash script

### 1. Install Command-line version

```bash
sudo apt install git p7zip-full python3-pip python3-wxgtk4.0 grub2-common grub-pc-bin wimtools
```

### 2. Download WoeUSB Bash Script

Go to GitHub, here is the [Link](https://github.com/WoeUSB/WoeUSB/releases/) and download the latest release:

![image](https://github.com/ShubhamKumar89/woeUSB/assets/97805339/586be5fc-0655-4b77-becd-9d7b1077e2c7)

Make the file executable: 

```bash
chmod +x woeusb-5.2.4.bash
./woeusb-5.2.4.bash
```
