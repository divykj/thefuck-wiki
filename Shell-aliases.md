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
function fuck {
    $fuck = $(thefuck (get-history -count 1).commandline)
    if($fuck.startswith("echo")) {
        $fuck.substring(5)
    }
    else { iex "$fuck" }
}
```

# tcsh

```tcsh
alias fuck 'set fucked_cmd=`history -h 2 | head -n 1` && eval `thefuck ${fucked_cmd}`'
```