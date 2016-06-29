# Bash

Add this alias to `.bashrc` or `.bash_profile` (for OSX):
```bash
eval "$(thefuck --alias)"
```

# ZSH

Add this alias to `.zshrc`:
```bash
eval "$(thefuck --alias)"
```

# Fish

Add this function to `config.fish`:
```fish
eval (thefuck --alias | tr '\n' ';')
```

# Powershell

Put this in your Powershell `$PROFILE` on Windows:

```powershell
iex "$(thefuck --alias)"
```

# tcsh

```tcsh
alias fuck 'set fucked_cmd=`history -h 2 | head -n 1` && eval `thefuck ${fucked_cmd}`'
```