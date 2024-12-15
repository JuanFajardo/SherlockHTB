__Name__

Brutus:hacktheblue

__Nivel__

Very Easy

__About Brutus__

In this very easy Sherlock, you will familiarize yourself with Unix auth.log and wtmp logs. We'll explore a scenario where a Confluence server was brute-forced via its SSH service. After gaining access to the server, the attacker performed additional activities, which we can track using auth.log. Although auth.log is primarily used for brute-force analysis, we will delve into the full potential of this artifact in our investigation, including aspects of privilege escalation, persistence, and even some visibility into command execution.

__Comandos__

1.
```bash
grep -i --color "accept" auth.log

Mar  6 06:19:54 ip-172-31-35-28 sshd[1465]: Accepted password for root from 203.101.190.9 port 42825 ssh2
Mar  6 06:31:40 ip-172-31-35-28 sshd[2411]: Accepted password for root from 65.2.161.68 port 34782 ssh2
Mar  6 06:32:44 ip-172-31-35-28 sshd[2491]: Accepted password for root from 65.2.161.68 port 53184 ssh2
Mar  6 06:37:34 ip-172-31-35-28 sshd[2667]: Accepted password for cyberjunkie from 65.2.161.68 port 43260 ssh2

grep -i --color "accept" auth.log | cut -d " " -f 12
```

2.
```bash
grep -i --color "accept" auth.log

Mar  6 06:19:54 ip-172-31-35-28 sshd[1465]: Accepted password for root from 203.101.190.9 port 42825 ssh2
Mar  6 06:31:40 ip-172-31-35-28 sshd[2411]: Accepted password for root from 65.2.161.68 port 34782 ssh2
Mar  6 06:32:44 ip-172-31-35-28 sshd[2491]: Accepted password for root from 65.2.161.68 port 53184 ssh2
Mar  6 06:37:34 ip-172-31-35-28 sshd[2667]: Accepted password for cyberjunkie from 65.2.161.68 port 43260 ssh2

grep -i --color "accept" auth.log | cut -d " " -f 10
```

3.
```bash
grep -in --color "accept" auth.log

utmpdump wtmp | grep "65.2.161.68"

Utmp dump of wtmp
[7] [02549] [ts/1] [root    ] [pts/1       ] [65.2.161.68         ] [65.2.161.68    ] [2024-03-06T06:32:45,387923+00:00]
[7] [02667] [ts/1] [cyberjunkie] [pts/1       ] [65.2.161.68         ] [65.2.161.68    ] [2024-03-06T06:37:35,475575+00:00]
```

4.
```bash
grep -in --color "accept" auth.log

grep -in "session" auth.log | grep "root"
```

5.
```bash
grep -in --color "add" auth.log

```

6.
```bash
https://attack.mitre.org/techniques/T1136/
```

7.
```bash
https://www.calculator.net/time-duration-calculator.html
```

8.
```bash
grep -in --color "sudo" auth.log
```
