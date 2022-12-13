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


# 3e : sudo docker ps 
```
CONTAINER ID   IMAGE     COMMAND                  CREATED              STATUS              PORTS                                   NAMES
c5cd94537900   nginx     "/docker-entrypoint.…"   About a minute ago   Up About a minute   0.0.0.0:8080->80/tcp, :::8080->80/tcp   web
```

Puis : sudo docker kill c5cd94537900

# 3f : sudo docker run -it --rm -d -p 8080:80 --name web nginx

# 3f : sudo docker cp $(pwd)/html/index.html index.html:/usr/share/nginx/html
 
 
# 4b : sudo docker build -t webserver .

# 4b : sudo docker run -it --rm -d -p 8080:80 --name web webserver

# 4c : mount ou copy.

- La solution mount se fait en ligne de commande et nécessite un chemin d'accès exact.
- La solution copy, elle, permet d'utiliser le chemin actuel comme chemin d'accès. 

- La solution mount est plus sécurisée, puisqu'on est sûr d'utiliser le bon dossier. Mais nécessite d'être tapée et sans fautes.

- La solution copy permet de ne pas retaper le path à chaque fois, mais peut être mal utilisée si le fichier est placé au mauvais endroit.

