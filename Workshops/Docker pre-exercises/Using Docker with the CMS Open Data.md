# Docker pre-exercises
---
## Using Docker with the CMS Open Data
This module will talk about Docker, and how we will use it with CMS Open Data. So, you will be able to use the interface CMS Open Data correctly. 

First, a docker image contains exactly rules and the enviorenment that the developer used in a moment.
This concept was reviewed deeply before. So, for now we need to use the CMS image to create a container. This container will be the tool for the next practices.

### 1. Downloading a CMS image
The first step, it's downloanding a specific image from CMS Open Data and create a container in order to work with it. We can use the next command in our terminal.

`docker run -it --name my_od -P -p 5901:5901 cmsopendata/cmssw_5_3_32_vnc:lastest /bin/bash`

### 2. Creating a CMS Container
After creating a container we'll need to start it. We can use this command. 

`docker start -i my_od`

### 3. Possible errors
We can find some errors in the process. These are we find the solution.

- Error 139
- CPU and Memory High

    #### Error 139
    To solve this we need to follow the next instructions.
    
    - Go to user folder in your system.
    - Using the bash stop wsl process with `wsl --shutdown`
    - Using the bash or another tool create a file called ".wslconfig"
    - Into it write the next lines
    
        `[wsl2]`

        `guiApplications=false`
        
        `kernelCommandLine = vsyscall=emulate`
    
    - Now you can start again the wsl process opening Docker.
    
    #### CPU and Memory High
    To solve this we need to follow the next instructions.
    
    - Go to user folder in your system.
    - Using the bash stop wsl process with `wsl --shutdown`
    - Using the bash or another tool create a file called ".wslconfig". You can only add the next lines if you already have the file instead.
    - Into it write the next lines
    
        `[wsl2]`

        `memory=1GB`
        
        `processors=2`
    
    - Now you can start again the wsl process opening Docker.



