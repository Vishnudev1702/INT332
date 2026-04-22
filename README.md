# Docker Practical Exam Guide – INT332

Student: Vishnu Dev

This single document contains the main Docker practical commands used in the lab.

------------------------------------
1. Check Docker Installation
------------------------------------
docker --version
docker info

------------------------------------
2. Pull Docker Image
------------------------------------
docker pull httpd
docker images

------------------------------------
3. Run Apache Container
------------------------------------
docker run -d --name apache-web -p 8080:80 httpd
docker ps

Open in browser:
http://localhost:8080

------------------------------------
4. Stop and Remove Container
------------------------------------
docker stop apache-web
docker rm apache-web
docker rmi httpd

------------------------------------
5. Run Ubuntu Container
------------------------------------
docker run -it ubuntu /bin/bash
exit

------------------------------------
6. Environment Variable Example
------------------------------------
docker run -it -e COLLEGE=CSE ubuntu bash
echo $COLLEGE

------------------------------------
7. Access Running Container
------------------------------------
docker exec -it <container_id> bash

------------------------------------
8. Container Interaction with Host
------------------------------------
docker exec -it mycontainer ls /
docker exec -it mycontainer /bin/bash

mkdir /data
echo "Hello Docker" > /data/test.txt
exit

Copy file container → host
docker cp mycontainer:/data/test.txt ~/Desktop/

Copy file host → container
docker cp ~/Desktop/test.txt mycontainer:/data/sample.txt

Verify
docker exec -it mycontainer ls /data
docker exec -it mycontainer cat /data/sample.txt

------------------------------------
9. MySQL Container
------------------------------------
docker run -d -p 3307:3306 --name mysql-test -e MYSQL_ROOT_PASSWORD=root123 mysql

docker exec -it mysql-test bash

mysql -u root -p
Password: root123

------------------------------------
10. Nginx Container
------------------------------------
docker pull nginx
docker run -d -p 8080:80 --name mynginx nginx

docker ps

Browser:
http://localhost:8080

docker stop mynginx
docker rm mynginx

------------------------------------
11. Docker Volume Example
------------------------------------
docker volume create mydata
docker volume ls

docker run -dit --name mycontainer -v mydata:/app/data ubuntu

docker exec -it mycontainer ls /app/data

docker rm -f mycontainer
docker volume rm mydata

------------------------------------
12. Cleanup Commands
------------------------------------
docker stop $(docker ps -aq)
docker rm $(docker ps -aq)
docker rmi $(docker images -q)
docker system prune -a

------------------------------------
Most Important Commands for Exam
------------------------------------
docker pull
docker images
docker run
docker ps
docker exec
docker stop
docker rm
docker rmi
docker volume create
docker cp
