# Installation

```powershell
git clone --bare https://github.com/nicholasdille/dotfiles-windows $env:UserProfile\Documents\.cfg
function config { git --git-dir=$env:UserProfile\Documents\.cfg --work-tree=$env:UserProfile @args }
config config --local status.showUntrackedFiles no
config checkout
```

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
