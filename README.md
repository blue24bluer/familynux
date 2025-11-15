
# FamilyNux

FamilyNux is a universal package-manager wrapper designed to unify different Linux and BSD package managers under one simple command. It automatically detects the system's native package manager and maps its functions to an APT-style interface.

This tool makes switching between distributions easier by providing a consistent workflow across different environments.

---

## Features

- Automatic detection of the system’s package manager:
  - apt
  - dnf
  - yum
  - pacman
  - pkg (FreeBSD / BSD)
- Unified apt-like command interface
- Wrapper scripts for each package manager
- Auto-installer (`start.py`) that installs the correct wrapper to `/bin/`
- Lightweight, portable, and distro-friendly

---

## Project Structure

```

familynux/
│
├── start.py
├── dnf2apt.sh
├── yum2apt.sh
├── pacman2apt.sh
├── pkg2apt.sh
└── familynux   (generated in /bin/ after install)

```

---

## How It Works

1. `start.py` detects your system’s package manager.
2. It chooses the matching script:
   - dnf2apt.sh
   - yum2apt.sh
   - pacman2apt.sh
   - pkg2apt.sh
   - or a direct apt wrapper
3. Installs the correct wrapper into `/bin/familynux`
4. You use `familynux` just like apt:

```

familynux install htop
familynux remove nano
familynux update
familynux search python

```

---

## Installation

Run the installer:

```

sudo python3 start.py

```

This installs the `familynux` command into `/bin/`.

---

## Usage

```

familynux <command> [package] [options]

```

### Examples

```

familynux update
familynux upgrade
familynux install neofetch
familynux remove firefox
familynux search nginx
familynux show python3

```

---

## Supported Commands

- update  
- upgrade  
- install  
- remove  
- autoremove  
- search  
- show  
- list  
- clean  
- check  
- depends  

---

## Supported Systems

- Debian / Ubuntu / Mint (APT)  
- Fedora / RHEL / Rocky / AlmaLinux (DNF)  
- CentOS 7 / Legacy RHEL (YUM)  
- Arch / Manjaro / BlackArch (PACMAN)  
- FreeBSD / TrueOS / DragonFly (PKG)  

---

## Notes

- Installation must be performed as root.
- All wrapper scripts must be in the same directory as `start.py` during installation.

---

## License

This project by @blue24bluer
