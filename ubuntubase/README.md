## How to use

### Build Docker Image
> docker build --tag cpp/work:0.1 .

### Run Docker Container
> docker run --name cppwork -v c:\DATA\Docker\DockerVolumes\cppwork:/home/oh/shared -it cpp/work:0.1

## Using Docker-Compose
### Build Image & Create Container as Deamon
> docker-compose up -d (command "up" needs option "-d")

### Stop Container
> docker-compose stop

### Re-start Container
> docker-compose start

### Stop & Remove Container
> docker-compose down
