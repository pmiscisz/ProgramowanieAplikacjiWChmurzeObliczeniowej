# BUILD
```
docker build --build-arg VERSION=2.5 -t lab5 .
```
![image](screenshots\Dockerbuild.png)
# RUN
```
docker run -d -p 8080:80 --name lab5_container lab5
```
![image](screenshots\Dockerrun.png)
# TEST
```
docker ps
```
![image](screenshots\wyniktestuhealthcheck.png)

# WIDOKSTRONY

![image](screenshots\widokstrony.png)
