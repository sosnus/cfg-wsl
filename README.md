# scripts ( old name: cfg-wsl) (aka old wsl-sosnus-support)

## merged rpi-scripts into this repo
## FAQ

### WSL run WSL2
https://learn.microsoft.com/pl-pl/windows/wsl/install-manual#step-4---download-the-linux-kernel-update-package
1. install update from file
2. wsl.exe --update
3. wsl --set-default-version 2
4. wsl.exe --install --no-distribution
5. restart PC

#### WSL error
The WSL optional component is not enabled. Please enable it and try again.
See https://aka.ms/wslinstall for details.
Error: 0x8007007e
Press any key to continue...

PowerShell as Admin
```
Enable-WindowsOptionalFeature -Online -FeatureName Microsoft-Windows-Subsystem-Linux
```

Also:

`DISM /Online /Enable-Feature /All /FeatureName:Microsoft-Hyper-V`
`bcdedit /set hypervisorlaunchtype auto`

https://github.com/microsoft/WSL/issues/5363#issuecomment-640337948

#### WSL2 update download
```
https://learn.microsoft.com/en-us/windows/wsl/install-manual#step-4---download-the-linux-kernel-update-package
```


## install-misc.sh contains:
* sl
* git (and config)
* fetchscreen
* tmux
* figlet

## BASH Ubuntu Debian snippets .sh
### Watch
run script in loop with interval
``` bash
watch -n 600 <command> <flags>
```
(do it forever, where -n is interval in seconds)
for example:
``` bash
watch -n 600 python3 main.py
```

Bash alternative to watch
while true; do ./my_script.sh; sleep 60; don
remember about `tmux`!


## TODO:
* add parameters
* add remmina or other RDP
* clean azure folder
* add turbo-config-scripts
* full-compatible Ubuntu-Debian-Raspbian
* better python config
* new installer logger (like start.sh)
* turbo config (on start select packages and programs)
