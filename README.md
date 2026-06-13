# CachyOS Repository Installer

This script automates the process of adding the CachyOS repositories to any Arch Linux-based distribution. CachyOS provides heavily optimized kernels and packages tailored for modern CPUs.

The script automatically detects your CPU's supported architecture (such as x86-64-v3, x86-64-v4, or znver4/5) and configures `pacman` to use the most optimal repositories for your specific hardware.

## Features

* Automatically detects CPU instruction set capabilities (x86-64-v3, x86-64-v4, znver4/5).
* Installs CachyOS keyring and mirrorlist.
* Backs up your current `/etc/pacman.conf` before making any modifications.
* Configures `/etc/pacman.conf` with the appropriate CachyOS repositories.
* Refreshes pacman databases automatically.
* Provides an easy removal option to revert changes.

## Requirements

* An Arch Linux-based distribution (Arch Linux, EndeavourOS, Manjaro, Garuda, etc.)
* `sudo` or root privileges
* `git` (to clone this repository)

## Step-by-Step Usage

### 1. Clone the repository

First, download the script to your local machine:

```bash
git clone https://github.com/your-username/cachyos-repo.git
```
*(Note: Replace the URL with your actual GitHub repository URL once uploaded)*

### 2. Navigate to the directory

```bash
cd cachyos-repo
```

### 3. Make the script executable

```bash
chmod +x cachyos-repo.sh
```

### 4. Run the script

Execute the script with root privileges to install the repositories:

```bash
sudo ./cachyos-repo.sh
```

Alternatively, you can explicitly use the install flag:

```bash
sudo ./cachyos-repo.sh --install
```

### 5. Install CachyOS Kernels and Packages

Once the script finishes successfully, the repositories are added. You can now install CachyOS kernels or other optimized packages. For example:

```bash
sudo pacman -S linux-cachyos linux-cachyos-headers
```

## How to Remove

If you want to remove the CachyOS repositories and revert your `pacman.conf` to its original state, run the script with the `--remove` flag:

```bash
sudo ./cachyos-repo.sh --remove
```
This will restore the backup of your `pacman.conf`, remove the CachyOS mirrorlist and keyring, and perform a system update to sync repositories.

## License

This project is licensed under the GNU General Public License v2.0 or later.
