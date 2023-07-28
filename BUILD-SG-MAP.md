# Method 1: use codespace
In github website: https://github.com/yilumistudio/openmaptiles, switch to "buildsgmap" branch.  
Chose "code" button at top right, select codespace, launch a new codespace or reopen the previous one.  

# Method 2: use local machine
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
