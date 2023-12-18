## Purpose of this repo
This repo contains a modified version of openmaptiles.yaml and other mapping and layer files.  
We don't use the openmaptiles tool (quickstart) to generate the tiles. Instead, we use  
yilumistudio/planetiler-openmaptiles to generate the tiles. But yilumistudio/planetiler-openmaptiles  
needs openmaptiles.yaml therefore we also maintain this repo.

## Purpose of customize scheme
Planetiler needs to access a hosted openmaptiles.yaml and relevant mapping and  
layer.yaml files to generate its tables and definitions.

## How to host locally
The original planetiler/Generate.java requires to access a hard coded url pattern  
on github. Local hosting of openmaptiles.yaml and others is handy during dev.  

To locally host openmaptiles.yaml and others:
```
# cd root of this repo
python3 -m http.server 23222
```

It will host all files in this repo on localhost:23222. Remember to forward this  
port in vs code if this **localhost** is a wsl ubuntu on Windows.

## Planetiler Generate.java
You should read https://github.com/yilumistudio/planetiler-openmaptiles/blob/main/sgmap-team/SGMAP-TEAM-README.md  
if you are not familiar with planetiler.

```
# In yilumistudio/planetiler-openmaptiles repo, run this to generate if locally hosted. 
# Note that this require Generate.java to be modified to recognize the key word "local".
./scripts/regenerate-openmaptiles.sh local http://localhost:23222/

# Otherwise, once released on github, run this to generate.
./scripts/regenerate-openmaptiles.sh version https://raw.githubusercontent.com/yilumistudio/openmaptiles/
```