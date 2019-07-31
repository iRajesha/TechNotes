# Docker search
`docker search myImage/container`

# Docker list of images
`docker images`

# Docker remove
`docker rm {container_name_OR_container_id}  and docker rmi {image}  `

# Docker remove all images and containers
docker system prune
docker system prune --volumes
docker container ls -a

docker rm -vf $(docker ps -a -q)
docker rmi -f $(docker images -a -q)

# To map the Host IP port to container port use
docker run -p 80:5000 container_name

# Data persistence in containers
use `-v` volumes to map the host directory to container directory

# Run docker in -d and attach mode as per your convenient 
 `Docker inspect container_id` will give you much more information about container

# Build your own image

1. Choose a base image
2. Create a docker build file
3. Add instructions to install required dependancy softwares
4. copy all the things required from volumes 
5. run the docker build file
6. use docker push command to push it to docker hub

# Use docker history command to check the history of operations 
# Use docker-compose files to create a bunch of containers together - Pretty crazy !


