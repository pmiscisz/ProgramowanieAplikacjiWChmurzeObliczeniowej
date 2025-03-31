# BUILD
```
docker build -f Dockerfile -t local/s2:1 . 
```
![image](/lab5/screenshots/Dockerbuild.png)
# RUN
```
docker run --rm -d -p 8080:80 --name=s2 local/s2:1
```
![image](/lab5/screenshots/Dockerrun.png)
# TEST
```
docker ps
```
![image](/lab5/screenshots/wyniktestuhealthcheck.png)

# WIDOKSTRONY

![image](/lab5/screenshots/widokstrony.png)
