# How to run this 

1. Build the image 

```
docker build -t my-ubuntu-apache2
```

1. Run docker container

```
docker start -d -p 81:80 --name my-apache-container my-ubuntu-apache2
```