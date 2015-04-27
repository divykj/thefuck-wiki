# Bash and Zsh

Add this alias to `.bashrc` or `.zshrc` or `.bash_profile` (for OSX):
```bash
alias fuck='eval $(thefuck $(fc -ln -1))'
```

# Fish

Add this function to `config.fish`:
```fish
function fuck
    eval (thefuck $history[1])
end
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