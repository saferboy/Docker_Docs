#  Container and localhost port binding (mapping)

### Dockerfile commands
- **[Dockerfile](https://docs.docker.com/engine/reference/builder/
)**
---
> ### `docker image ls` 

| CONTAINER ID | IMAGE |    COMMAND    |      CREATED      | STATUS |        PORTS         |           NAMES |
| :----------- | :---: | :-----------: | :---------------: | :----: | :------------------: | --------------: |
| 9ac3f734435c | nginx | "/entrypoint" |   7 seconds ago   |   Up   |        80/tcp        |     zen_hermann |
| 2eea293c6eec | nginx |  /entrypoint  | About an hour ago |  exit  | 127.0.0.1:82->80/tcp |      menza_aker |
| b2d0a00b082c | nginx | "/entrypoint" | About an hour ago |  Exit  |  0.0.0.0:81->80/tcp  | nostalgic_knuth |


> ### `PORT = 80/tcp` - if the port is not given a local port, it will be open only inside the container and we will not be able to connect to it from outside. for example = 80/tcp


> ## 1. Port mapping
> ### If the local port has been used before, i.e. it is busy, I can give you an empty port
> ### `docker container run -d -p 80:80 nginx`
>  - `-d` - start the container in the detouch method
>  - `-p` - for us to give a port to the container
>  - <span style="color:white">80 : <span style="color: yellow">80</span> </span> **nginx**
>    - <span style="color:white">80</span> - local port on the computer
>    - <span style="color:yellow">80</span> - The default port where the container is running
 

> ## 2. Port mapping to the specified IP address
>
> ### `0.0.0.0:81->80/tcp` - these 4 zeros represent all IP addresses on the local computer
>
> ### if we do not specify the IP address while doing port mapping, the mapping local will be set to all ports on the computer
>
> ### `docker container run-d -p 127.0.0.1:80:80 nginx`
>  - `127.0.0.1` - computer IP address
> 
>    - `ipconfig` - To view all IP addresses on a Windows
>    - `ifconfig` - To view all IP addresses on a Mac


> ## 3. Mapping multiple ports at once
> ### To map multiple ports at once, serialize ports with the -p switch
> ### `docker container run -d -p 83:80 -p 333:333 nginx`
> 
>   - -p <span style="color:yellow">83 : <span style="color:white">83 </span></span> -p <span style="color:red">333 : <span style="color:green">333 </span></span>
>
>     - <span style="color:yellow">83</span> - local port
>     - <span style="color:white">83</span> - container port
>     - <span style="color:red">333</span> - local port
>     - <span style="color:green">333</span> - container port


> ### 4. Mapping multiple consecutive ports at once
>
> ###  <span style="color:white">docker container run -d -p <span style="color:red">3000-3200</span> : <span style="color:yellow">3000-3200</span> nginx</span>
>
>   - <span style="color:red">3000-3200</span>  - local port
>   - <span style="color:yellow">3000-3200</span>  - container port


