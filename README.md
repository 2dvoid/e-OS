# e-OS

![Badge](https://img.shields.io/badge/Base-Arch_Linux-1793d1?style=for-the-badge&logo=arch-linux&logoColor=white)
![Badge](https://img.shields.io/badge/WM-Sway-2e3440?style=for-the-badge&logo=sway&logoColor=white)
![Badge](https://img.shields.io/badge/Status-Stable-success?style=for-the-badge)

e-OS is a portable development environment built on Arch Linux.

Designed as a specialized **Live Distro**, it is engineered to run entirely from a USB drive, instantly transforming any computer into a highly efficient development environment without installation.

---

## ⚡ Core Philosophy
Rejecting the visual bloat of modern operating systems, e-OS adopts a strict **"function over form"** philosophy. It prioritizes raw speed, keyboard-driven efficiency, and essentialism. It doesn't care about looking pretty; it cares about getting the job done.

### 🚀 Zero-Config Development
**Boot and code.** The environment comes pre-provisioned with a fully configured compiler, interpreter, and Neovim setup. There is no post-install setup, no "ricing" required, and no time wasted. You jump straight into the code.

### ⌨️ Keyboard-Centric Workflow
**Mouse interaction is obsolete.** Every action—from launching apps to managing windows—is mapped to intuitive keybindings. The workflow is engineered to keep your hands on the home row, maximizing speed and reducing context switching.

### 🗔 Efficient Window Management
**Focus on logic, not layout.** The Sway window manager automatically snaps applications into efficient tiling grids. You never drag, resize, or minimize windows; the system manages your screen real estate so you can manage your code.

### 💿 The Portable Arsenal
**Your workstation, anywhere.** e-OS is designed to live on a USB drive. It provides a consistent, high-performance development environment on any hardware you encounter, without leaving a trace on the host machine.


## 📸 Screenshots

| Login Screen | Sway Desktop |
| :---: | :---: |
| ![Login](https://via.placeholder.com/400x225?text=Login+Screen) | ![Desktop](https://via.placeholder.com/400x225?text=Sway+Desktop) |


## 🛠️ Building from Source

To build **e-OS** yourself, you need an Arch Linux system with the `archiso` package installed.

### 1. Prerequisites
```bash
sudo pacman -S archiso git
```

### 2. Clone the Repository
```bash
git clone [https://github.com/yourusername/e-OS.git](https://github.com/yourusername/e-OS.git)
cd e-OS
```

### 3. Build the ISO
This command uses your local disk for the working directory (safer than RAM) and outputs the ISO to the `out/` folder.

```bash
# Clean previous builds (optional)
sudo rm -rf work out

# Run the build script
sudo mkarchiso -v -w work -o out .
```

*Build time: 5-15 minutes depending on internet connection and CPU.*

### 4. Burn to USB
Once the build is complete, you can find the ISO in the `out/` directory. Flash it using `dd` or Etcher.

```bash
# Replace /dev/sdX with your USB drive identifier
sudo dd bs=4M if=out/e-OS-v1.0-x86_64.iso of=/dev/sdX status=progress oflag=sync
```

---
