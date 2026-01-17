<div align="center">
  
# / e-OS /

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



## 🏗️ Build Instructions

Clone the repo and build the ISO with a single command:

```bash
# 1. Install dependencies
sudo pacman -S archiso git

# 2. Clone the Repository
git clone https://github.com/2dvoid/e-OS.git
cd e-OS

# 3. Build the ISO
# ISO file will built in the out/ directory
sudo mkarchiso -v -w work -o out .

# 3. Burn to USB
sudo dd if=e-OS-*.iso of=/dev/sdX bs=4M status=progress oflag=sync
```
