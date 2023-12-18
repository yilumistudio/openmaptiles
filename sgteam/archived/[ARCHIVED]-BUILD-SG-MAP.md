# Method 1: use codespace
In github website: https://github.com/yilumistudio/openmaptiles, switch to "buildsgmap" branch.  
Chose "code" button at top right, select codespace, launch a new codespace or reopen the previous one.  

# Method 2: use local machine
## How to install ubuntu on windows using wsl.
wsl is the latest technology from Windows to install virtual linux machine.  
Follow this article: https://learn.microsoft.com/en-us/windows/wsl/install  
After installation, make sure in Windows powershell, 
`wsl -l -v`  
This should print ubuntu as one of the distribution (distro).  

You will need to set up default user and password other than root.  
If wsl --install let you create your default user, do it there. Otherwise, you can also  
mannually create the default ubuntu user as follows:  
```
# assume in root account
adduser user-name
apt update
visudo
```
In the sudoer's list, add these under %sudo line  
`username   ALL=(ALL) ALL`  
If the editor is "Gnu Nano", use "ctrl o, hit enter" to save, "ctrl x" to exit.  
You can check whether this user is in sudoer's list:
`sudo -l -U username`  
It should print username may run ALL commands.  

Now set this user to be the default ubuntu user  
```
# still in root account
touch /etc/wsl.conf
nano /etc/wsl.conf
```
Write these content  in wsl.conf
```
[user]
default=username
```
Now, type "exit" to exit terminal. 

## Go back to ubuntu terminal
In windows start menu, type "ubuntu" to go to ubutun terminal.  
It should use the new default user.  

## Use vs code in wsl ubuntu
You don't need to install vs code for linux. Instead, you can use windows VS code to connect to wsl ubuntu.
### terminal way
In ubuntu terminal, type  
`code directory/to/open`  

### windows way
In windows vs code, click bottom left blue button, connect to wsl with distro, select ubuntu.  

### 
In either way, your vs code should display "WSL" at bottom left area, and you terminal should show the default  
ubuntu user name. 

## Other setups
Install make,  
```
sudo apt update
sudo apt install make
```
Install gh (github)
`sudo apt install gh`  

Set up github credential. You can try clone the repo.
`gh repo clone yilumistudio/openmaptiles`  
You will be asked for logins. Use token way as wsl ubuntu has no browser. 

## Install docker on Windows (host)
Install docker desktop on Windows if hasn't. This wsl ubuntu openmaptiles repo will use host docker for  
making map tiles.
   
# Build SG map
In codespace or local wsl ubuntu repo,  
Run:  
```
make
./quickstart.sh singapore
```

# Don't delete containers and volumes created during make and ./quickstart.sh