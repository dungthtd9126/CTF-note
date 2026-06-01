# CTF-note
## github command

Connect local terminal to github for remote updates:
```bash
git remote add origin https://github.com/dungthtd9126/CTF-event.git
```
- git remote add: This tells Git, "I want to create a new connection to a remote server."

- origin: This is just a shortcut name. Instead of making you type out the long GitHub URL every single time you want to push or pull code, Git lets you save it under a nickname. origin is the standard, universally used nickname for your main repository.

- [https://github.com/dungthtd9126/CTF-event.git](https://github.com/dungthtd9126/CTF-event.git): This is the exact destination URL being attached to the nickname "origin".

## Modify partition and disk space
- sudo gparted &
## enter daila env
- source daila_env/bin/activate

## set visualize max chunk size
- set max-visualize-chunk-size 0x500

## Unikey tool on arch
- Enable unikey arch tool: fcitx5-configtool

## update all packages
- paru -Syu

## firejail 
- firejail --private ./your_exploit_binary

## scan virus
- clamscan -r ~/Downloads
