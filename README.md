# Docker with Web App 

## Docker Container: Centos 7, Apache, and PHP 7.2
```bash
# cd into docker-webapp directory
cd docker-webapp

#create a docker image
docker build -t image_apache .

#run docker, change <container name> to your own name, <local/path/to/file> to your own path where the assets are located
docker run -tid -p 4000:80 --name=<container name> -v <local/path/to/file>:/var/www/html image_apache



## Log
Here is a sample run ...

```sh
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

(base) ➜  docker-webapp pwd
(base) ➜  docker-webapp docker run -tid -p 4000:80 --name=container_apache -v /Users/anhkimhoang/Documents/GitHub/docker-webapp:/var/www/html image_apache
935dfe254e171dc5fb9287d7f964ff05a4040459936c9a7855fb7861333fd9c1

# now go to localhost:4000
```
