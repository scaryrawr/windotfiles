# Windows Dot Files!?!??!

So... I've been setting up more customizations on Windows machines,
and thought it would be easier to do something like the whole dotfiles
repository that we do on Linux.

Please see [The best way to store your dotfiles: A bare Git repository](https://www.atlassian.com/git/tutorials/dotfiles)
for some insight.

Fun fact, if you use OneDrive, PowerShell profile syncs through that (if you have your Documents folder Location set as
OneDrive/Documents).

Magic alias pair, this is how you set up the config command in PowerShell in a similar way to Linux dotfiles.

```powershell
# Clone bare repository in home directory
git clone --bare https://github.com/scaryrawr/windotfiles $HOME/.dotfiles

# Create alias helper
function Update-Config {
	& git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME $args
}

# Create alias for working with dotfiles
Set-Alias -Name config -Value Update-Config

# Set not to show untracked files
config config --local status.showUntrackedFiles no

# "Reset" to unstage all "changes"
config reset

# "Revert" all local changes
config checkout .
```
