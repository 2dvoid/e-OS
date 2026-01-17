<div align="center">
  
# e-OS

![Distro](https://img.shields.io/badge/Distro-Arch_Linux-1793d1?style=for-the-badge&logo=arch-linux&logoColor=white)
![WM](https://img.shields.io/badge/WM-Sway-30363F?style=for-the-badge&logo=sway&logoColor=white)
![Editor](https://img.shields.io/badge/Editor-Neovim-57A143?style=for-the-badge&logo=neovim&logoColor=white)
![Type](https://img.shields.io/badge/Type-Live_ISO-285577?style=for-the-badge&logo=usb&logoColor=white)
![Status](https://img.shields.io/badge/Status-Stable-success?style=for-the-badge)
![Release](https://img.shields.io/github/v/release/yourusername/e-OS?style=for-the-badge&logo=github&logoColor=white&color=285577)

<p>
<b>e-OS</b> is a portable workspace designed for developers who need to move fast. It is a full Arch Linux system that runs entirely from a USB drive, allowing you to carry your tools in your pocket. There is no installation or setup required—just plug it in, boot up, and you have a consistent, distraction-free environment ready for code.
</p>

</div>

## 📸 Showcase

![nvdash](https://github.com/user-attachments/assets/0c7e2c8f-8940-42ea-9c18-7456768d2d05)
<img src="https://nvchad.com/banner.webp">

<img src="https://nvchad.com/screenshots/onedark.webp">


## ⚡ Features

* 🎒 **Portable:** Your entire workspace fits in your pocket. Runs entirely form a USB drive.
* ✨ **Zero Setup:** No installation required. Boot up and you are instantly ready to develop.
* ⌨️ **Keyboard First:** Mouse-free efficiency. Every action is mapped to a keybinding so your hands never leave the home row.
* 🪟 **Auto-Tiling:** Powered by Sway. Windows snap into logical grids automatically—no more manual dragging or resizing.
* 🛠️ **Dev-Ready:** Comes pre-loaded with a fully configured coding environment (Neovim, git, compilers).



## ⚙️ Configuration

Want to change the defaults before building? Here is how to tweak the source:

* 📦 **Add Software:** Edit `packages.x86_64` to add or remove packages from the ISO.
* 🎨 **Dotfiles:** Modify `airootfs/etc/skel/.config` to change the default Sway, Neovim, or Zsh configs for new users.
* 🖼️ **Wallpapers:** Drop your images into `airootfs/.config/background` and `airootfs/.config/lockscreen` to bake them into the build.
* 🚀 **Services:** Place startups units in `airootfs/etc/systemd/system` to enable them during boot.


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
