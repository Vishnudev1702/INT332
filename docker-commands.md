# Docker Practical Commands

## Pull Image
docker pull httpd

## List Images
docker images

## Run Apache Container
docker run -d --name apache-web -p 8080:80 httpd

## List Running Containers
docker ps

## Stop Container
docker stop apache-web

## Remove Container
docker rm apache-web

## Remove Image
docker rmi httpd