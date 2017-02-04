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
thefuck --alias | source 
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

# xonsh

Install the xonsh extension:
```
pip install xontrib-thefuck
```

And then load it (you can add this to xonshrc for it to be loaded in every xonsh session):
```
xontrib load thefuck
```
