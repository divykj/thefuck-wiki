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

>_If you use oh-my-zsh, try [this awesome *thefuck* plugin](https://github.com/robbyrussell/oh-my-zsh/blob/master/plugins/thefuck/README.md)._

# Fish

Add this function to `config.fish`:
```fish
thefuck --alias | source 
```

To avoid the delay of the shell startup, you could also create an [autoloaded function](https://fishshell.com/docs/current/tutorial.html#tut_autoload).
Create a file `~/.config/fish/functions/fuck.fish` instead and paste the output of `thefuck --alias` 
into that file. Fish should start as fast as before.

For cases when you override a command and turn it into an alias (e.g. `alias sed=gsed` or `alias git=hub`), you should add all them to the `THEFUCK_OVERRIDDEN_ALIASES` environment variable, separated by comma. For example, in your `config.fish`:

```fish
set -x THEFUCK_OVERRIDDEN_ALIASES 'gsed,git'
```

# Powershell

Put this in your Powershell `$PROFILE` on Windows:

```powershell
iex "$(thefuck --alias)"
```

To overcome Python unicode [warning](https://github.com/nvbn/thefuck/issues/514) on your unicode Powershell console:
```powershell
c:\python3\lib\site-packages\win_unicode_console\__init__.py:31: RuntimeWarning: sys.stdin.encoding == 'utf-8', whereas sys.stdout.encoding == 'ascii', readline hook consumer may assume they are the same
  readline_hook.enable(use_pyreadline=use_pyreadline)
```

Add this line **before** the line above in your Powershell `$PROFILE` on Windows:

```powershell
$env:PYTHONIOENCODING="utf-8"
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

# Troubleshooting

If the following error message is shown when trying to run `thefuck`:

```
command not found: thefuck
```

Ensure that `~/.local/bin` is present in your path. eg. add `PATH="$PATH:$HOME/.local/bin"` to `.bashrc`, `.zshrc` etc.