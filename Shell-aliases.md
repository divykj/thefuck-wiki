# Bash

Add this alias to `.bashrc` or `.bash_profile` (for OSX):
```bash
eval "$(thefuck --alias)"
```

# ZSH

Add this alias to `.zshrc`:
```bash
alias fuck='$(thefuck $(fc -ln -1 | tail -n 1)); fc -R'
```

# Fish

Add this function to `config.fish`:
```fish
function fuck -d 'Correct your previous console command'
    set -l exit_code $status
    set -l eval_script (mktemp 2>/dev/null ; or mktemp -t 'thefuck')
    set -l fucked_up_commandd $history[1]
    thefuck $fucked_up_commandd > $eval_script
    . $eval_script
    rm $eval_script
    if test $exit_code -ne 0
        history --delete $fucked_up_commandd
    end
end
```

Alternatively, you can redirect the output of `thefuck-alias`:
```bash
 ~> thefuck --alias >> ~/.config/fish/config.fish
```

Or, yet, you can create a function:
```bash
 ~> thefuck --alias > ~/.config/fish/functions/fuck.fish
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