# Method 1: use codespace
In github website: https://github.com/yilumistudio/openmaptiles, switch to "buildsgmap" branch.  
Chose "code" button at top right, select codespace, launch a new codespace or reopen the previous one.  

# Method 2: use local machine
## Preparation: 
1. must use non-Windows machine. E.g. Mac or Linux
2. After clone the repo, switch to branch "buildsgmap" first, and pull from github
   ```
   git checkout buildsgmap
   git pull origin buildsgmap
   ```
# Build SG map
Run:  
`./quickstart.sh singapore`
