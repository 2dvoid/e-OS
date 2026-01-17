<div align="center">
  
# e-OS

![Distro](https://img.shields.io/badge/Distro-Arch_Linux-1793d1?style=for-the-badge&logo=arch-linux&logoColor=white)
![WM](https://img.shields.io/badge/WM-Sway-30363F?style=for-the-badge&logo=sway&logoColor=white)
![Editor](https://img.shields.io/badge/Editor-Neovim-57A143?style=for-the-badge&logo=neovim&logoColor=white)
![Type](https://img.shields.io/badge/Type-Live_ISO-285577?style=for-the-badge&logo=usb&logoColor=white)
![Status](https://img.shields.io/badge/Status-Stable-success?style=for-the-badge)
![Release](https://img.shields.io/github/v/release/yourusername/e-OS?style=for-the-badge&logo=github&logoColor=white&color=285577)

<p>
e-OS is a portable workspace designed for developers who need to move fast. It is a full Arch Linux system that runs entirely from a USB drive, allowing you to carry your tools in your pocket. There is no installation or setup required—just plug it in, boot up, and you have a consistent, distraction-free environment ready for code.
</p>

</div>

## 📸 Showcase

| Login Screen | Sway Desktop |
| :---: | :---: |
| ![Login](https://via.placeholder.com/400x225?text=Login+Screen) | ![Desktop](https://via.placeholder.com/400x225?text=Sway+Desktop) |



## ⚡ Features
Rejecting the visual bloat of modern operating systems, e-OS adopts a strict **"function over form"** philosophy. It prioritizes raw speed, keyboard-driven efficiency, and essentialism. It doesn't care about looking pretty; it cares about getting the job done.

### 🚀 Zero-Config Development
**Boot and code.** The environment comes pre-provisioned with a fully configured compiler, interpreter, and Neovim setup. There is no post-install setup, no "ricing" required, and no time wasted. You jump straight into the code.

### ⌨️ Keyboard-Centric Workflow
**Mouse interaction is obsolete.** Every action—from launching apps to managing windows—is mapped to intuitive keybindings. The workflow is engineered to keep your hands on the home row, maximizing speed and reducing context switching.

### 🗔 Efficient Window Management
**Focus on logic, not layout.** The Sway window manager automatically snaps applications into efficient tiling grids. You never drag, resize, or minimize windows; the system manages your screen real estate so you can manage your code.

### 💿 The Portable Arsenal
**Your workstation, anywhere.** e-OS is designed to live on a USB drive. It provides a consistent, high-performance development environment on any hardware you encounter, without leaving a trace on the host machine.


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
