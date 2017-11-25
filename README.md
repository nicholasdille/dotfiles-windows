# Installation

```powershell
git clone --bare https://github.com/nicholasdille/dotfiles-windows $env:UserProfile\Documents\.cfg
function config { git --git-dir=$env:UserProfile\Documents\.cfg --work-tree=$env:UserProfile @args }
config config --local status.showUntrackedFiles no
config checkout
```
