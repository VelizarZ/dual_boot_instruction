# Dual Boot Linux Distro Alongside Windows

This guide will help you dual boot a Linux distribution alongside Windows on your PC. Additionally, it covers how to disable BitLocker in Windows before proceeding with the Linux installation.

## Prerequisites

Before starting the process, make sure you have the following:

- A USB drive (at least 8GB) for creating a bootable Linux USB.
- A Windows PC with enough storage space for a dual boot setup.
- Backup important data to avoid accidental loss.

## Step 1: Prepare Windows for Dual Boot

1. **Free Up Disk Space**: 
   - Open `Disk Management` in Windows by searching for it in the Start Menu.
   - Right-click on the Windows partition (C:) and select `Shrink Volume`.
   - Allocate enough space for Linux (at least 20GB recommended).
   - Leave the newly created space as "Unallocated."

2. **Disable BitLocker (If Applicable)**:
   - Open the Start Menu and go to `Settings` > `Privacy & Security`.
   - Under `Device Encryption`, click on `Device encryption`.
   - If device encryption is enabled, click on `Turn off` and follow the instructions to disable it.
   - Wait for the decryption process to complete before proceeding. **Important:** This step is necessary if BitLocker or device encryption is enabled, as it can interfere with the Linux bootloader.


3. **Disable Fast Startup**:
   - Go to `Control Panel` > `Hardware and Sound` > `Power Options` > `Choose what the power buttons do`.
   - Click `Change settings that are currently unavailable`.
   - Uncheck `Turn on fast startup (recommended)` and save the changes.

## Step 2: Create a Bootable Linux USB

1. Download your preferred Linux distribution from its official website (e.g., Ubuntu, Fedora, etc.).
2. Use a tool like [Rufus](https://rufus.ie/) or [Etcher](https://www.balena.io/etcher/) to create a bootable USB drive with the Linux ISO file.

## Step 3: Install Linux Alongside Windows

1. Insert the bootable USB drive and reboot your PC.
2. Enter the BIOS/UEFI settings (usually by pressing `F2`, `DEL`, or `ESC` during boot).
3. Change the boot order to boot from the USB drive first.
4. Once the Linux installer starts, select the option to install Linux **alongside Windows**.
5. Choose the partition created earlier (unallocated space) for Linux and proceed with the installation.

## Step 4: Set Up the Bootloader

During installation, the Linux installer will install a bootloader (usually GRUB) that allows you to choose between Linux and Windows at startup.

- After installation, reboot your PC.
- You will be presented with a boot menu where you can choose to boot into either Linux or Windows.

## Step 5: Post-Installation Setup

Once the installation is complete, consider the following:

- **Update Linux**: Open a terminal in your Linux installation and run the update command specific to your distribution (e.g., `sudo apt update && sudo apt upgrade` for Ubuntu).
- **Install Drivers**: Ensure you have the latest drivers for your hardware, especially if you're using an Nvidia GPU or similar.

## Troubleshooting

- **GRUB Not Showing**: If the GRUB bootloader doesn't appear, you may need to access your UEFI/BIOS settings and disable `Secure Boot`.
- **Windows Boot Issues**: If Windows doesn't boot, boot into Linux and run `sudo update-grub` to update the bootloader configuration.

## Additional Resources

- [Ubuntu Dual Boot Guide](https://ubuntu.com/tutorials/install-ubuntu-desktop#1-overview)
- [How to Disable BitLocker in Windows 10](https://support.microsoft.com/en-us/windows/turn-off-bitlocker-decryption-9b3b1151-57b3-c202-d5a0-719a8e9c55fb)
- [Rufus - Bootable USB Creation](https://rufus.ie/)

---
By following this guide, you can successfully dual boot a Linux distribution alongside Windows, ensuring you have access to both operating systems on your PC.
