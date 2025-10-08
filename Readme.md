# Arch Linux Automated Installer

## Overview

This project is an automated Arch Linux installer script that aims to make the process of installing Arch Linux fast, reliable, and user-friendly. The script guides users through essential installation steps, automating complex tasks and reducing the potential for errors. It is designed to be run from an official Arch Linux ISO environment.

## Features

- **Interactive Guided Setup:** The script provides a menu-driven interface for selecting installation options, making it accessible for both beginners and advanced users.
- **Automated Disk Partitioning:** Supports various filesystem and encryption options, including LUKS for full disk encryption.
- **User and Host Configuration:** Automates the creation of users, groups, and hostname setup.
- **Package Installation:** Installs essential packages such as GRUB, NetworkManager, and microcode updates for Intel and AMD CPUs.
- **Graphics Driver Detection:** Automatically detects and installs the appropriate drivers for NVIDIA, AMD, and Intel graphics hardware.
- **System Tweaks:** Enables parallel downloads, color output, and the "ILoveCandy" easter egg in pacman, and configures sudo access for the wheel group.
- **Post-Installation Script:** Generates a final setup script to be run in the chrooted environment, ensuring all configurations are applied.

## How It Works

1. **Pre-Installation Checks:** Verifies that the script is running as root, in an Arch ISO environment, and not inside a Docker container.
2. **User Input:** Prompts the user for key installation parameters such as username, password, machine name, disk selection, and filesystem type.
3. **Disk Setup:** Partitions and formats the selected disk according to user preferences, with optional encryption.
4. **Base System Installation:** Uses `pacstrap` to install the base system and essential packages.
5. **Chroot Configuration:** Writes and executes a secondary script inside the new system to finalize configuration, install drivers, and set up users.
6. **Finalization:** Installs and configures the bootloader, enables networking, and prepares the system for first boot.

## Requirements

- Arch Linux ISO (latest recommended)
- Internet connection
- Target machine with supported hardware

## Usage

1. Boot from the Arch Linux ISO.
2. Run the following commands
```bash
pacman -Syu git curl 
```
3. Clone the Repository
```bash
git clone https://github.com/dhruvmistry2000/archmitra"
cd archmitra
```
4. Run the script as root:
   ```bash
   bash setup.sh
   ```
5. Follow the on-screen prompts to complete the installation.

## Disclaimer

This script is provided as-is and should be reviewed before use. It is intended for educational purposes and to assist with rapid Arch Linux deployments. Always back up important data before proceeding with any automated installation process.