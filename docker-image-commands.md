# Docker Image Documentation

> ### **View a list of images in docker**
>
> ### `docker image ls -a`


> ### **Download Image by default**
>
> ### `docker image pull 'image name:tag'`
>
> > - **image nomi**
> > - **tag can be given, if not given, the 'latest' tag will be given by default docker**


> ### To see how much space the images take up on the computer
>
> > ### `docker system df`
> > -   **view all images** 
>
> > ### `docker image df [OPTIONS] REPOSITORY[:TAG]`
> > ### `docker image df (image name)`
> > - **view only one image**


> ### Building a Docker Image using DockerFile
>
> ### Inside the folder where the Dockerfile is located, there should also be an index.html file
>
> ```json
>     #Docker  file
>
>	FROM debian:buster-slim
>
>	RUN apt-get update
>	RUN apt-get install -y nginx
>
>	COPY ./index1.html /var/www/html
>
>	#shell form
>	CMD nginx -g 'daemon off;'
>
>	#exac form, this recommended form  
>	# CMD ["nginx", "-g", "daemon off"
> ``` 
> - `debian:buster-slim` - This Image contains the debian buster slim version and runs on this system
> - `apt-get update` - This command is used to update debian packages
> - `apt-get install -y nginx` - This command installs the nginx server
> - - `-y` - this command does not ask for confirmation during installation
> - `COPY ./index1.html /var/www/html` - This command will copy the index1.html file from your local files to the Docker Image and move it to the web display directory (/var/www/html) for the Nginx server. Changes can be made instead of this file
> - `CMD nginx -g 'daemon off` - This command starts the Nginx server. This command starts the Nginx server in basic mode with "daemon off"
>
> ### Creating a Docker Image
> ### `docker image build -t mynginx:v1.0.0 .`
>   - `docker image build` - this command tells docker to create a new image
>   - `-t 'new image name:tag'` - with this command you can give a new name and tag to the image
>   - `.` - specifies the folder where the image should be created to docker, must be in the same folder as the Dockerfile

> ### Starting the Container based on the created image
>
> ### Container works on port 80 by default, mapping the port inside the container to the port on the local computer
>
> ### `docker container run -itd -p 80:80 mynginx:v1.0.0`
>   - `-itd` - this command represents the following
>   - - `-i` - Works in interactive mode, providing communication between your terminal and the container
>   - - `-t` - Tmux provides the use of a terminal emulator
>   - - `-d` - Runs the container in the background (daemon) mode, which means you can run it in another terminal window
>   - - `-p 80:80` - This shorthand is used to link the port of the host system (80) and the port of the container (80). This binds port 80 of the host system to port 80 of the Docker container at the time of the listened request
> - `docker exec -it <CONTAINER_ID> /bin/bash` - - If you want to manage the container to make changes with the terminal, you can access the container with the following command



> ### Run Image
> ### The image will be searched from the local repository, if not, it will be automatically downloaded from the Docker hub
>
> ### `docker image run hello-world` 


> ## Delete Image
>
> ### To delete an image from the local repository, its name or ID must be given
> ### `docker image rm hello-world:latest` 
> ### If the image is running as a container, it cannot be deleted
> ### There are 2 different ways to delete it
> > ### 1. Delete the container first, then delete the image
>
> > ### 2. `docker image rm -f hello-world:latest`
> > - `-f` or `--force` - this command will delete the image even if it is running
>
> ### To delete all unused images
>
> ### `docker image prune`