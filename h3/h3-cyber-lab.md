# h3 Cyber Lab

In this task, we take the first steps on our own cyber lab.

First of all, quick recap from Tero's articles:

## [Command Line Basics Revisited, Tero Karvinen](https://terokarvinen.com/2020/command-line-basics-revisited/)

* Quick refresher on essential shell skills: `pwd`, `ls`, `cd`, `less` for everyday navigation and viewing.
* File manipulation: `cp`, `mv`, `rm`, `mkdir`. Big caution: `rm` has no trash!
* Remote work with `ssh` / `scp` and basic admin tips (`sudo`, package management with `apt`).
* Productivity hacks: tab completion, command history (`history`, `Ctrl-R`), and `man` / `--help` for help.
* Practical guidance on important filesystem paths (`/etc`, `/home`, `/var/log`) and safe admin practices. 

## [Cracking Passwords with Hashcat — Tero Karvinen](https://terokarvinen.com/2022/cracking-passwords-with-hashcat/)

* Explains that systems store hashes (one-way) not passwords, and password cracking tries guesses to match hashes.
* Shows setup steps: install `hashcat`, `hashid`, and download large wordlists (e.g., `rockyou.txt`) for dictionary attacks.
* Identify the hash type first (use `hashid` or compare to example hashes). Hashcat needs the correct `-m` mode.
* Demonstrates practical cracking approaches (dictionary attacks, using big wordlists) and stresses legal/ethical use.

## Presentation Title

_**Stop Hard-Coding Secrets: Practical API Security in Spring Boot**_

## Installing Debian 13-Trixie on a Virtual Machine (Short Report)

I installed Debian 13-Trixie in a virtual machine to prepare a secure Linux environment for cybersecurity and development practice.

I downloaded the Debian 13 "Live Xfce" ISO image from the official website and created a new VM in VirtualBox. I configured the VM according to the installation walkthrough in the class. I attached the ISO and launched the Graphical Install.

During installation, I selected language and region settings and created a user account. After installation, the system rebooted into Debian successfully.

The VM runs smoothly and is ready for Linux command-line and cybersecurity exercises.

## Cracking Passwords with Hashcat
I installed `hashcat` and followed the steps in the article to crack the example hash. Unfortunatelly I faced an error `* Device #1: Not enough allocatable device memory for this attack.`. I am trying to figure out the issue and increase the memory of VM and see how it goes.
Once done with this, I'll try to do John the Ripper (Install and test John the Ripper Jumbo).
