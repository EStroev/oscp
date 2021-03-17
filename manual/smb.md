# SMB

## Enumeration

```text
smbclient -L //x.x.x.x -N
```

```text
smbclient //HOST/PATH -c 'recurse;ls' PASS -U USER
```

## Scanning

```text
nmap --script smb-vuln* -p139,445 -T4 -Pn 10.11.1.111
```

## Command Execution

```text
winexe -U username //<ip> "cmd.exe" –system
```

