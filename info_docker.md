
**Dockerization**\

**Create docker iamge**\

```
docker build -t my-flask-image:latest .
```
**Vulnerabilidades**
```
docker scout quickview
```
**Ver las imagenes existentes**
```
docker images
```
**Ejecutar imagen**

```
docker run -d -p 5000:5000 my-flask-image
```
```
docker exec -it my-flask-image bash
```
**Dockerfile**
```
FROM ubuntu:18.04
RUN apt-get update -y
RUN apt-get install -y python-pip python-dev build-essential
ADD . /pyflask
WORKDIR /pyflask
RUN  pip install -r requirements.txt 
ENTRYPOINT ["python"]
CMD ["hm-docker.py"]
```

**Requirements file**
```
Flask==1.1.4
```

**Issues**

```
sudo vi ~/.docker/config.json
ERROR: failed to solve: ubuntu:18.04: failed to resolve source metadata for docker.io/library/ubuntu:18.04: error getting credentials - err: exec: "docker-credential-desktop": executable file not found in $PATH, out: ``

https://stackoverflow.com/questions/65896681/exec-docker-credential-desktop-exe-executable-file-not-found-in-path
```



