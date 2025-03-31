# BUILD
```
docker build -f Dockerfile -t local/s2:1 . 
```
![image](/Dockerbuild.png)
# RUN
```
docker run --rm -d -p 8080:80 --name=s2 local/s2:1
```
![image](/Dockerrun.png)
# TEST
```
docker ps
```
![image](/wyniktestuhealthcheck.png)

# WIDOKSTRONY

![image](/widokstrony.png)
