## How to use

### Build Docker Image
> docker build --tag cicd/build:0.1 .

### Run Docker Container
> docker run --name buildnode -v C:\DATA\Docker\DockerVolumes\cicd\build:/home/oh/shared -it cicd/build:0.1

## Using Docker-Compose
### Build Image & Create Container as Deamon
> docker-compose up -d (command "up" needs option "-d")

### Stop Container
> docker-compose stop

### Re-start Container
> docker-compose start

### Stop & Remove Container
> docker-compose down
