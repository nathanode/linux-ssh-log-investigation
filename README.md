# SSH Log Investigation Using Linux

## About This Project

This is my first cybersecurity investigation project using Linux.

I've been learning Linux commands and wanted to see how they could be used in a real cybersecurity role, particularly as a SOC analyst.

For this project, I worked with a simulated SSH log file containing different login attempts. My aim was to look through the logs, identify anything suspicious and explain what I thought might have happened.

## Tools Used

- Ubuntu Linux (WSL)
- Linux terminal
- Git and GitHub

## What I Did

I started by looking through a log file called `ssh_security.log`, which contained 10 login events.

I used a few Linux commands to help me investigate:

| Command | What I Used It For |
|---|---|
| `wc -l ssh_security.log` | Counted how many entries were in the log |
| `grep -i "failed" ssh_security.log` | Found all the failed login attempts |
| `grep -ic "failed" ssh_security.log` | Counted the failed login attempts |
| `tail -n 1 ssh_security.log` | Checked the last login event |
| `grep "admin" ssh_security.log` | Looked at login activity involving the admin account |

## What I Found

While looking through the logs, I noticed something suspicious involving the `admin` account.

There were four failed login attempts in a row, followed by a successful login.

The attempts happened between 10:02 and 10:06, and they all came from the same IP address: `203.0.113.50`.

This stood out to me because someone could have been trying different passwords until they managed to log in.

I also noticed another user, `bob`, had one failed login followed by a successful login. I thought the activity involving `admin` was more concerning because there were several failed attempts close together.

## My Thoughts

At first, seeing multiple failed logins followed by a successful one made me think someone might have gained unauthorised access.

However, I learned that suspicious activity doesn't automatically mean a cyberattack has happened.

If I was investigating this further, I would want to check whether the login was authorised, whether any files had been accessed or changed, and whether any unusual activity happened after the successful login.

## What I Learned

This project helped me understand how Linux commands can be used to investigate security logs rather than just manage files and folders.

I also learned how important it is to look at the evidence before deciding whether something is actually a security incident.

I'm still at the beginning of learning cybersecurity, but I enjoyed doing this investigation and want to work on more challenging projects as my skills improve.

---

**Note:** This was a guided learning exercise using simulated log data, not a real security incident.# linux-ssh-log-investigation
Beginner SOC investigation analysing simulated SSH authentication logs using Linux.
