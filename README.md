# Docker with Web App 

## Docker Container: Centos 7, Apache, and PHP 7.2
```bash
# cd into docker-webapp directory
cd docker-webapp

#create a docker image
docker build -t image_apache .

#run docker, change <container name> to your own name, <local/path/to/file> to your own path where the assets are located
docker run -tid -p 4000:80 --name=<container name> -v <local/path/to/file>:/var/www/html image_apache
```


## Log
Here is a sample run ...

```bash
docker build -t image_apache .
Sending build context to Docker daemon   2.56kB
Step 1/9 : FROM centos:7
 ---> 67fa590cfc1c
Step 2/9 : RUN yum -y update
 ---> Running in 76475d125732
Loaded plugins: fastestmirror, ovl
Determining fastest mirrors
 * base: mirror.umd.edu
 * extras: mirror.umd.edu
 * updates: mirror.umd.edu
Resolving Dependencies
--> Running transaction check
---> Package audit-libs.x86_64 0:2.8.4-4.el7 will be updated
---> Package audit-libs.x86_64 0:2.8.5-4.el7 will be an update
---> Package bash.x86_64 0:4.2.46-31.el7 will be updated
---> Package bash.x86_64 0:4.2.46-33.el7 will be an update

... [omitted from log]

#new image with port 4040
base) ➜  docker-webapp git:(master) ✗ docker run -tid -p 4040:80 --name=centos7test -v /Users/anhkimhoang/Documents/GitHub/docker-webapp/centos7-apache/var/www/html/:/var/www/html image_apache
ccd845af7f4841a1aa24a9cccbd4809c6f517fa6c6df98b9fcc7076d9c9cb947
(base) ➜  docker-webapp git:(master) ✗
```
