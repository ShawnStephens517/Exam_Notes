# Target: <BOX_NAME> (<PLATFORM>)

**Difficulty:** <Easy/Medium/Hard>
**OS:** <Linux/Windows>
**Date:** {{date}}
**Tags:** #htb #writeup #<VULN_TYPE> #<OS>

---

## 1. High-Level Summary
The box **<BOX_NAME>** demonstrates a classic vulnerability in **<SERVICE>** leading to initial foothold. Privilege escalation required abusing **<MISCONFIGURATION>** to execute code as root.

**Key Skills Learned:**
* Enumerating <SERVICE_NAME> versions manually.
* Modifying public exploit code (CVE-XXXX-XXXX).
* Abusing SUID binaries for root access.

---

## 2. Enumeration

### Nmap Scan
```bash
nmap -p- -sC -sV <TARGET_IP> --min-rate 1000
```

- **Port 22:** SSH
    
- **Port 80:** HTTP (Apache 2.4.41)
    

### Service Enumeration (Port 80)

Initial directory busting revealed a `/backup` folder containing...

![[assets/dirbuster_results.png]]

---

## 3. Foothold (Exploitation)

**Vulnerability:** <VULN_NAME> (CVE-20XX-XXXX)

I found a public exploit for this version, but it required modification to work with the target architecture.

**Exploit Script:** [exploit.py](https://www.google.com/search?q=./scripts/exploit.py)

**Execution:**

Bash
