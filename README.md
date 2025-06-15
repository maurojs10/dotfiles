# My Personal dotfiles Managed by chezmoi

A collection of my personal configuration files for various tools that I use.

> [!WARNING]  
> This repository is for my private use only and not intended for public distribution or use.

> [!IMPORTANT]  
> Before installing on WSL, edit file `/etc/wsl.conf` and add the following lines:
> ```
> [automount]
> options="metadata,umask=022,fmask=011"
> ```

<details>
<summary><b>Installation on Windows</b></summary>

1. Start [PowerShell](https://learn.microsoft.com/powershell/scripting/windows-powershell/starting-windows-powershell).

2. Install [Chocolatey](https://chocolatey.org) as administrator:

   ```console
   Start-Process powershell '-NoProfile -ExecutionPolicy Bypass -Command "irm https://community.chocolatey.org/install.ps1 | iex"' -Verb RunAs -Wait
   ```

3. Set PowerShell execution policy:

   ```console
   Set-ExecutionPolicy RemoteSigned Process -Force
   ```

3. Refresh current session environment:

   ```console
   Import-Module "$env:ProgramData\chocolatey\helpers\chocolateyInstaller.psm1"; refreshenv
   ```

4. Install [chezmoi](https://www.chezmoi.io) via [Chocolatey](https://community.chocolatey.org/packages/chezmoi):

   ```console
   Start-Process choco 'install chezmoi -y' -Verb RunAs -Wait
   ```

6. Initialize chezmoi and apply the configurations:

   ```console
   chezmoi init --apply maurojs10
   ```
</details>

<details>
<summary><b>Installation on Ubuntu</b></summary>

1. Open [Terminal](https://ubuntu.com/tutorials/command-line-for-beginners#3-opening-a-terminal).

2. Ensure Ubuntu is updated:

   ```console
   sudo apt update \
   && sudo apt upgrade -y \
   && sudo apt autoremove -y
   ```

3. Install [chezmoi](https://www.chezmoi.io) via [Snap](https://snapcraft.io/chezmoi):

   ```console
   sudo snap install chezmoi --classic
   ```

4. Initialize chezmoi and apply the configurations:

   ```console
   chezmoi init --apply maurojs10
   ```
</details>

<details>
<summary><b>Installation on macOS</b></summary>

1. Open [Terminal](https://support.apple.com/guide/terminal/open-or-quit-terminal-apd5265185d-f365-44cb-8b09-71a064a42125).

2. Install [Homebrew](https://brew.sh):

   ```console
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```

3. Install [chezmoi](https://www.chezmoi.io) via [Homebrew](https://formulae.brew.sh/formula/chezmoi):

   ```console
   brew install chezmoi
   ```

4. Initialize chezmoi and apply the configurations:

   ```console
   chezmoi init --apply maurojs10
   ```
</details>
