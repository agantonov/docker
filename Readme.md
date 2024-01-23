### Build Ubuntu Docker image
```
$ sudo docker build --tag ubuntu-host:0.01 -f ubuntu-host/Dockerfile .
```

### Run Docker Container
```
$ sudo docker run -d --name ubuntu-host --cap-add=NET_ADMIN ubuntu-host:0.01
```

### Stop Docker Container
```
$ sudo docker stop ubuntu-host
```

### Delete Docker Container
```
$ sudo docker rm ubuntu-host
```

### Delete Docker Image
```
$ sudo docker image rm -f ubuntu-host:0.01
```
