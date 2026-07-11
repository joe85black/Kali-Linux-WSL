# Kali Linux on WSL

Step-by-step guide to installing WSL2 + Kali Linux, with GUI support (Win-KeX) and Zsh as the default shell.

## 1. Install or enable WSL 2

Open PowerShell as Administrator and run:

```powershell
wsl --install
```

This installs WSL, the WSL 2 kernel, and Ubuntu by default. (Alternatively, enable the features manually with DISM and restart.)

## 2. Ensure WSL 2 is the default version

```powershell
wsl --set-default-version 2
```

## 3. Install Kali Linux

In PowerShell (Admin):

```powershell
wsl --install -d kali-linux
```

Set up a username + password after install.

## 4. Update Kali

Inside Kali, update packages:

```bash
sudo apt update && sudo apt full-upgrade -y
```

Optional — install a full suite of Kali tools:

```bash
sudo apt install -y kali-linux-large
```

## 5. Install Win-KeX (GUI support)

Inside Kali, run:

```bash
sudo apt update
sudo apt install -y kali-win-kex
```

## 6. Launch a GUI session

Win-KeX supports 3 modes:

- **Window mode** (desktop in a window): `kex --win -s`
- **Seamless mode** (apps integrated into Windows): `kex --sl -s`
- **Enhanced Session mode** (RDP-based rich session): `kex --esm --ip -s`

## 7. Install and configure Zsh

Zsh is a powerful alternative shell, often used with Kali.

Install Zsh:

```bash
sudo apt install -y zsh
```

Make Zsh your default shell:

```bash
chsh -s /bin/zsh
```

After installation, restart your Kali session or open a new terminal — your default shell will now be Zsh with enhanced functionality.

## 8. Optional enhancements

- Add a Win-KeX profile in Windows Terminal for quick launch.
- Use WSLg (Windows 11) to run Linux GUI apps directly without a full desktop.
