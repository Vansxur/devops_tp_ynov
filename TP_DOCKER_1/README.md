# TP DEVOPS

# 3a : sudo docker pull nginx

```
Using default tag: latest
latest: Pulling from library/nginx
025c56f98b67: Pull complete 
ca9c7f45d396: Pull complete 
ed6bd111fc08: Pull complete 
e25b13a5f70d: Pull complete 
9bbabac55ab6: Pull complete 
e5c9ba265ded: Pull complete 
Digest: sha256:ab589a3c466e347b1c0573be23356676df90cd7ce2dbf6ec332a5f0a8b5e59db
Status: Downloaded newer image for nginx:latest
docker.io/library/nginx:latest
```

# 3b : sudo docker images

```
REPOSITORY   TAG       IMAGE ID       CREATED        SIZE
nginx        latest    ac8efec875ce   11 hours ago   142MB
```

# 3c : mkdir html
- cd html 
- touch index.html
- echo "Hello World" >> index.html

# 3d : sudo docker run -it --rm -d -p 8080:80 --name web -v $(pwd)/html/:/usr/share/nginx/html nginx

