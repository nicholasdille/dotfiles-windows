# Installation

```powershell
git clone --bare https://github.com/nicholasdille/dotfiles-windows $env:UserProfile\Documents\.cfg
function config { git --git-dir=$env:UserProfile\Documents\.cfg --work-tree=$env:UserProfile @args }
config config --local status.showUntrackedFiles no
config checkout --force
```

## Pretty prompts in PowerShell

You need to use a terminal emulator, like [ConEmu](https://conemu.github.io/) or [Cmder](http://cmder.net/). They can also be used [for WSL as described here](https://conemu.github.io/en/BashOnWindows.html).

The following commands will get you started with a nice prompt:

```powershell
Install-Module -Name PowerLine
Import-Module -Name PowerLine
Set-PowerLinePrompt -SetCurrentDirectory -RestoreVirtualTerminal -Newline -Timestamp -Colors "#00DDFF","#0066FF"
```

If you are looking for theme management, take a look at [oh-my-posh](https://github.com/JanJoris/oh-my-posh):

```powershell
Import-Module -Name posh-git, oh-my-posh
Set-Theme agnoster
```

You should be using the [PowerLine fonts](https://github.com/powerline/fonts/), [Nerd Fonts](https://github.com/ryanoasis/nerd-fonts) or [fonts from here](https://github.com/gabrielelana/awesome-terminal-fonts).

## Useful prerequisites

```powershell
Install-PackageProvider -Name chocolatey -Force
Import-PackageProvider -Name chocolatey
Set-PackageSource -Name chocolatey -Trusted

Install-Module PSReadline
Install-Module PSScriptAnalyzer
Install-Module PSDeploy
Install-Module Pester
Install-Module ISESteroids
Install-Module PSake
Install-Module PoshRunJob

Install-Package -Source chocolatey -Name git
Install-Package -Source chocolatey -Name posh-git
Install-Package -Source chocolatey -Name conemu

Invoke-WebRequest -Uri https://github.com/JanJoris/PS-Agnoster/raw/master/PS-Agnoster.ps1 -OutFile ~\Documents\WindowsPowerShell\Scripts\PS-Agnoster.ps1

Install-Package -Source chocolatey -Name visualstudiocode-insiders
Install-Package -Source chocolatey -Name ruby
Install-Package -Source chocolatey -Name vlc
Install-Package -Source chocolatey -Name rdm

Install-Module PowerForensicsv2
```
