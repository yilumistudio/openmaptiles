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
Now, type "exit" to exit terminal. In windows start menu, type "ubuntu" to go to ubutun terminal.  
It should use the new default user.  


## Preparation: 
1. must use non-Windows machine. E.g. Mac or Linux
2. Install VS code in dev machine. Install these extensions: docker and devcontainer  
3. After clone the repo, switch to branch "buildsgmap" first, and pull from github
   ```
   git checkout buildsgmap
   git pull origin buildsgmap
   ```
4. Reopen VS code, as the repo has a .devcontainer set up, it should prompt for opening dev container
   Accept it and now it's using a docker container to build map tiles.
   
# Build SG map
In codespace or local dev container,  
Run:  
`./quickstart.sh singapore`
