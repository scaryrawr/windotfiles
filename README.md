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
function Update-Config {
	& git --git-dir=$HOME/.dotfiles/ --work-tree=$HOME $args
}

Set-Alias -Name config -Value Update-Config
```
