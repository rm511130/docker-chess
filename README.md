# Docker-Chess

Let's run my Chess PHP App using Docker.

Make sure you have Docker installed and running on your Mac and follow the steps below:

```
Mac $ cd /work
Mac $ git clone https://github.com/rm511130/docker-chess
Mac $ cd docker-chess
Mac $ docker build . -t chess
Mac $ docker run -d --rm -p 8080:80 chess
```

Access the Chess App using a browser: http://127.0.0.1:8080

![](./chess.jpg)

To stop the Docker Chess program, follow this example:

```
Mac $ docker ps

CONTAINER ID   IMAGE  COMMAND                  CREATED              STATUS              PORTS                 NAMES
1eaebd33e42b   chess  "docker-php-entrypoi…"   About a minute ago   Up About a minute   0.0.0.0:8080->80/tcp  pedantic_yalow

Mac $ docker stop 1eaebd33e42b
```

# Now let's push the Docker image of Chess to the Docker Hub

These are the steps I executed to upload the Docker Chess App image to my Docker Hub repo:

```
Mac $ docker image tag chess rmeira/chess
Mac $ docker push rmeira/chess
```
```
The push refers to repository [docker.io/rmeira/chess]
be49f33c8be0: Pushed 
4859737e9cf0: Pushed 
fcaa1dcf61a3: Pushed 
0fe12bb58fe8: Pushed 
2c74367a1f2c: Pushed 
a616f8ab5356: Mounted from library/php 
079d43545924: Mounted from library/php 
d97484483f49: Mounted from library/php 
b242745ebda2: Mounted from library/php 
d0d3b2f87351: Mounted from library/php 
be73e3c8f219: Mounted from library/php 
0fc284fc9cf5: Mounted from library/php 
732057c800a3: Mounted from library/php 
4cc11613548d: Mounted from library/php 
df6c050501b6: Mounted from library/php 
b4bfb20b5f05: Mounted from library/php 
2e8cc9f5313f: Mounted from library/php 
f2cb0ecef392: Mounted from library/php 
latest: digest: sha256:1e2f9674f4deabcca481312926a0a1fdf012e8d855363553a52b048171b98fc6 size: 4072
```

You can now run Docker Chess using the following command:

```
Mac $ docker run -d -p 8080:80 rmeira/chess
```

And access the Chess App using a browser: http://127.0.0.1:8080






