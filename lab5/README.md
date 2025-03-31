# BUILD
```
docker build -f Dockerfile -t local/s2:1 . 
```
![image](screenshots\Dockerbuild.png)
# RUN
```
docker run --rm -d -p 8080:80 --name=s2 local/s2:1
```
![image](screenshots\Dockerrun.png)
# TEST
```
docker ps
```
![image](screenshots\wyniktestuhealthcheck.png)

# WIDOKSTRONY

![image](screenshots\widokstrony.png)
