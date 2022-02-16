## How to use

### Build Docker Image
docker build --tag cpp/work:0.1 .

### Run Docker Container
docker run --name cppwork -v c:\DATA\Docker\DockerVolumes\cppwork:/home/oh/shared -it cpp/work:0.1