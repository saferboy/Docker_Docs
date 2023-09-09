# Deploy Docker Image to Docker Hub

> ### 1. log into docker hub in the terminal
>
>   ### `docker login`
>  - `username`
>  - `paswword`


> ### 2. You need to rename an existing Image with a different name
>
> ### `docker image tag imageName:ImageTag dockerhubUsername/newNameForImage:newTag`


> ### 3. Push the image
>
> ### `docker image push repostoryName/imagename:tag`