# Docker with Web App 

## Docker Container: Centos 7, Apache, and PHP 7.2
```bash
# cd into docker-webapp directory
cd docker-webapp

#create a docker image
docker build -t image_apache .

#run docker, change <container name> to your own name, <local/path/to/file> to your own path where the assets are located
docker run -tid -p 4000:80 --name=<container name> -v <local/path/to/file>:/var/www/html image_apache

