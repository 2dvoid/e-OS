# e-OS

![Badge](https://img.shields.io/badge/Base-Arch_Linux-1793d1?style=for-the-badge&logo=arch-linux&logoColor=white)
![Badge](https://img.shields.io/badge/WM-Sway-2e3440?style=for-the-badge&logo=sway&logoColor=white)
![Badge](https://img.shields.io/badge/Status-Stable-success?style=for-the-badge)

**e-OS** is a custom, minimalist Arch Linux ISO built for productivity and performance. It delivers a pre-configured Wayland environment (Sway) with a focus on "no-clown-fiesta" aesthetics—muted colors, distraction-free workflows, and developer-first tooling out of the box.

---

## ⚡ Features

* **Window Manager:** [Sway](https://swaywm.org/) (Wayland) pre-configured for tiling efficiency.
* **Terminal:** GPU-accelerated terminal (Kitty/Foot) with Zsh & custom prompts.
* **Editor:** Neovim pre-installed with a robust configuration (Plugins, LSPs).
* **Localization:** Native support for **Bengali (Bangla)** fonts and locales (`bn_BD`).
* **Live Environment:**
    * Auto-login user.
    * `sudo` privileges enabled (passwordless).
    * "Sanitized" config ensuring compatibility across different hardware.
* **Aesthetics:** Dark, muted theme designed to reduce eye strain.

## 📸 Screenshots

| Login Screen | Sway Desktop |
| :---: | :---: |
| ![Login](https://via.placeholder.com/400x225?text=Login+Screen) | ![Desktop](https://via.placeholder.com/400x225?text=Sway+Desktop) |

## 🚀 Getting Started

### Default Credentials
| User | Password | Sudo? |
| :--- | :--- | :--- |
| **e** | *(Empty)* | Yes (No Password) |
| **root** | *(Empty)* | Yes |

### Keybindings (Cheatsheet)
| Key Combination | Action |
| :--- | :--- |
| `Super` + `Enter` | Open Terminal |
| `Super` + `D` | Open Application Launcher (Wofi) |
| `Super` + `Shift` + `Q` | Kill Window |
| `Super` + `1-9` | Switch Workspaces |
| `Super` + `Shift` + `1-9` | Move Window to Workspace |

---

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

## 📂 Project Structure

* **`airootfs/`**: The root filesystem of the live OS.
    * `etc/skel/`: Dotfiles (Config) that get copied to the user's home.
    * `etc/systemd/`: Custom service overrides (Auto-login).
* **`packages.x86_64`**: List of packages installed on the ISO.
* **`profiledef.sh`**: Main configuration file (ISO Name, Label, Version).

## 🤝 Credits

* Built with [Archiso](https://wiki.archlinux.org/title/archiso).
* Configured with [Sway](https://swaywm.org/) and [Waybar](https://github.com/Alexays/Waybar).
* Fonts provided by [Nerd Fonts](https://www.nerdfonts.com/) and [Google Noto](https://fonts.google.com/noto).

---

> **Note:** This project is tailored for personal use but open for anyone who appreciates a minimal Arch setup.
