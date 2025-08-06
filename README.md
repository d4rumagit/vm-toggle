# vm-toggle
A simple shell script to toggle between VirtualBox and KVM on Linux without rebooting. 


A shell script to easily toggle between VirtualBox and KVM on Linux.  
VirtualBox cannot run when KVM is active because both require hardware virtualization (VT-x/AMD-V).  
This script unloads or loads the appropriate KVM modules, allowing you to switch modes without rebooting.

## Features
- Toggle between VirtualBox and KVM with one command
- Detects Intel or AMD CPUs automatically
- No reboot required
- Simple and lightweight

## Requirements
- Linux (Debian, Ubuntu, ParrotOS, or any system using `modprobe`)
- `sudo` privileges
- VirtualBox and/or KVM/QEMU installed

## Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/d4rumagit/vm-toggle.git
   cd vm-toggle
