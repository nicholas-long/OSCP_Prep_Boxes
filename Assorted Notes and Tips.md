# Enumeration
## gobuster not finding directories or files
* If you are having trouble finding something, try the dirb wordlists as a last resort, which are stored in `/usr/share/wordlists/`
> In the box "shocker" [[OSCP Preparation/linux/shocker/10 - enumeration]], the `cgi-bin` directory was not found from raft wordlists or directory-list-2.3. These lists contain `cgi-bin` in the wordlist, but without a slash. `cgi-bin/` is in the dirb wordlists.
* nikto should be used as a last of the last possible last resorts because it is the slowest thing ever made. Maybe run it while enumerating if it's starting to look like you won't find anything.
* check source and scripts
* check headers
* check CSS if you have to