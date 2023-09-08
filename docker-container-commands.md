# Docker Documentation

> ## docker
>
> `management commands` -  Designed to work with individual resources in Docker
> `commands` -   Commands used in previous version of Docker


> ## docker container ls
>  **`list of containers`**


>  ## docker sub commands
> 
> > ## `docker container ls -a`
> > - `container` - control command
> > - `ls` - sub command related to the container
> > - `-a` - additional key to see all containers that have worked so far 
> >    - `-a` = all


>   # Run container
> > ### 1. **start the container based on the image**
> > ### `docker container run -it alpine sh` 
> >
> > - `run` - **the key that starts the container**
> > - `-it` - **additional command to be able to work in the launched image terminal**
> > - `alpine` - **The run function is given the image name as a parameter**
> >     - `alpine` - **is an image of the linux operating system**
> > - `sh` - **terminal type**
>
> > ### 2. Start an existing container
> > - **container can be given a name during startup** 
> > - **if not given name, docker will choose a random name for it**
> > ### `docker container start (container_name)`
> > - `start` - **command to run only an existing container**
> > - `epic_shaw` - **for example, random container name**
>
> > ### 3. **To delete the container from memory when we stop it**
> > ### `docker container run --rm -it alpine sh` 
> > `The difference between a container started with this command and a container created in a normal way is that it is deleted from memory when it stops working or when the container is exited.`
> > - `--rm` - **short version of remove, This flag means to delete the container after it is finished running. This means that this command will delete the container it's written in after it's finished.**
> > - `-it`  - **opens a terminal to run in the container**
> > - `sh` - **terminal type**
>
> > ### 4. Naming the container when starting it
> > ### `docker container run --rm -it --name saferboy alpine sh`
> > ### `docker container run --rm -it --name=saferboy alpine sh`
> > - `--name` - **this key gives the specified name to the container**
>
> > ### 5. Start the container in the detouch method; that is, running the container in the background, the container is started but not entered
> > ### `docker container run --rm -itd --name=saferboy alpine sh` 
> > - `-itd` or `-d` - **this key will run the container in the background, and the terminal will not open**

> ## Stop the container
> > ### 1. Graceful 
> > ### `docker continer stop (container name)`
> > - **stop gracefully, default, correctly**
>
> > ### 2. Kill 
> > ### `docker container kill (container name)`
> > - **delete immediately**

>  ### Delete unused old container from memory
>  ### `docker container rm (container name)`
 

> ### All at once delete unused containers
> ### `docker container prune`

>  ### Inside the terminal; for information about the image
>  ### `cat /etc/os-release`

>  ### Connect to the container
>  ### **`docker container attach (container name)`**

> ### Exit the container
> ### `exit`


> ### Shows the client and server versions of docker
> ### `docker version`
