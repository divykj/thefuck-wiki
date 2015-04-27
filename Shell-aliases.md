# Bash and Zsh

Add this alias to `.bashrc` or `.zshrc` or `.bash_profile` (for OSX):
```bash
alias fuck='eval $(thefuck $(fc -ln -1))'
```

# Fish

Add these functions to `config.fish`:
```fish
function __thefuck_repl -d 'Replace operators into fish-compatible'
    set -l tmp (echo $argv | sed 's/ && / ; and /g')
    echo $tmp | sed 's/ || / ; or /g'
end

function fuck -d 'Correct your previous console command'
    set -l eval_script (mktemp 2>/dev/null ; or mktemp -t 'thefuck')
    thefuck $history[1] > $eval_script
    eval (__thefuck_repl (cat $eval_script))
    rm $eval_script
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