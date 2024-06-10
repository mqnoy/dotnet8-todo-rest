# Quick guidance for install and setup dotnet on linux

### i'm using debian 12 with zsh shell

Download
```
wget https://dot.net/v1/dotnet-install.sh -O dotnet-install.sh
```

Installing
```
chmod +x ./dotnet-install.sh
./dotnet-install.sh --version latest
```

Set environment variables system-wide.
```
export DOTNET_ROOT=$HOME/.dotnet
```

enable TAB completion for the .NET CLI
```
# zsh parameter completion for the dotnet CLI

_dotnet_zsh_complete()
{
  local completions=("$(dotnet complete "$words")")

  # If the completion list is empty, just continue with filename selection
  if [ -z "$completions" ]
  then
    _arguments '*::arguments: _normal'
    return
  fi

  # This is not a variable assignment, don't remove spaces!
  _values = "${(ps:\n:)completions}"
}

compdef _dotnet_zsh_complete dotnet
```

Link to usr/bin
```
sudo ln -s /home/imza/.dotnet/dotnet /usr/bin/dotnet
```