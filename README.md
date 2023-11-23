# HyprV4-OhMyZsh

This is a customized version of the HyprV4 installation script that not only installs the HyprV4 configurations but also sets up the zsh shell along with the Oh My Zsh framework.

The original script can be found in SolDoesTech's repository: [HyprV4](https://github.com/SolDoesTech/HyprV4).

## Overview

This repository houses a collection of dot config files tailored for Hyprland, accompanied by a straightforward installation script.

**Note: This script is intended for a clean, fresh Arch installation on physical hardware.**

### Installation Steps

#### 1. Setting Up a Clean Arch Linux Install

- For Spanish users: Use "**loadkeys es**" to switch the default English keyboard layout to Spanish.

- Get device to connect to your Wi-Fi:
  ```bash
  iwctl device list
  ```

- Connect to your Wi-Fi:
  ```bash
  iwctl --passphrase=[PASSPHRASE] station [DEVICE] connect [WIFI-NAME]
  ```

- Verify your Wi-Fi connection:
  ```bash
  ping 8.8.8.8
  ```
  If it returns packets, you're successfully connected to the internet.

- Run the "**archinstall**" script. Choose your preferred configurations, considering these options:
  - Select the **minimal** Profile option.
  - Select **Pipewire** in the audio.
  - Add the following additional packages: **git**, **nano**, **neofetch**.
  - Choose **NetworkManager** for network configuration.
  - Select **multilib** in the optional repos.

#### 2. Post Installation

- After the "**archinstall**" script completes, **do not chroot** into the newly created installation. Instead, reboot.

- Upon booting into Archlinux, connect to Wi-Fi using:
  ```bash
  nmcli device wifi connect [WIFI-NAME] password [PASSWORD]
  ```
  Verify your internet connection as previously instructed.

- Clone this config repository and execute the "**set-hypr**" script such as:
  ```bash
  git clone https://github.com/ItsZcx/HyprV4-OhMyZsh.git

  cd HyprV4-OhMyZsh

  ./set-hypr
  ```

Keyboard layout inside **HyprV/hypr/hyprland.conf** is set to **es** (spanish), in case you want to change it, replace **es** to **us**.

#### 3. In case you want to configurate Git:

Remember to install and configurate you git account, you can do it via this commands:

1. Configure your Git account:
    ```bash
    git config --global user.name "Name"
    git config --global user.email "your.email@example.com"
    ```

2. Install OpenSSH:
    ```bash
    sudo pacman -S openssh
    ```

3. Generate an SSH key:
    ```bash
    ssh-keygen
    ```

After generating the SSH key, navigate to your GitHub settings on the web and add the contents of the created file (typically located at .ssh/*.pub) to the SSH keys section.