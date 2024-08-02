```sh
docker build -t react-app .
```

# 000

# 001

# 002

# 003

# 004

# 005

# 006

# 007

# 008

# 009

# 010

# 011

# 012

# 013

# 014

# 015

# 016

# 017

# 018

# 019

# 020

# 021

# 022

# 023

# 024

# 025

# 026

# 027

# 028

# 029

# 030

# 031

# 032

# 033

# 034

# 035

# 036

create enriroment variables

```dockerfile
ENV API_URL=https://api.myapp.com/
```

print api url

```bash
printenv
```

```bash
printenv API_URL
```

```bash
echo $API__URL
```

# 037 exposing ports

# 038 setting the user

make a group and a user with the primary gruop
app app is the standarts in linux for docker shit

```sh
addgroup app
adduser -S -G app app
```

check is the app user does have the app group

```sh
groups app
```

```sh
addgroup fefe && adduser -S -G fefe fefe
```

```sh
whoami
```

# 039 defining entrypoints

shell form
this spins up a new shell

```sh
CMD npm start
```

exec form
this just runs the command directly

```sh
CMD ['npm','start']
```

this is more difficult to override
--entrypoint to override the command

```sh
ENTRYPOINT [ "executable" ]
```

# 040 speeding up builds

all the lines in the dockerfile are like different layers
user layer caching
to organize your build you should structure with the instructions that do not change frequently at the top

this speeds up the image because it can just re use the npm install the it did previusly

```sh
COPY package*.json .
RUN npm install
COPY . .
```

# 041 removeing images and containers

```sh
docker image prune
```

```sh
docker container prune
```

```sh
docker image rm <name></name>
docker image rm <id></id>
docker image rm <name></name> <name></name>
docker image rm <id></id> <id></id>
```

# 042 taggin images

```sh
docker build -t react-app:buster
docker build -t react-app:3.1.5
docker build -t react-app:77
```

re tag it

```sh
docker image tag <image name> <new image name>
```

# 043

go through this again set up the account

```sh

```

# 044 saving and loading images

```sh
docker image save -o react-app.tar react-app:2
```

```sh
docker image load -i react-app.tar
```

# 045 intro

starting and stopping containers
publishing pots
viewing logs
executing commands in containers
removing containser
persisting data using volumes
sharing source code

```sh

```

# 046 staring containers

run in the back ground with -d

```sh
docker run -d react-app
```

naming container so that you are not creating a new container every time you use run

```sh
docker run -d --name <name> react-app
```

# 047

```sh
docker logs <container>
```

```sh
docker logs -f <container>
```

number of line to show

```sh
docker logs -n 5 <container>
```

time stamps

```sh
docker logs -n 5 -t <container>
```

# 048 publishing ports

```sh
docker run -d -p 3000:3000 --name c1 react-app
```

# 049

```sh
docker exec c1 ls
```

```sh
docker exec -it c1 sh
```

# 050 stopping and starting container

```sh
docker stop <container name>
```

```sh
doker start <conatiner name>
```

# 051

force remove running container

```sh
docker rm -f c1
```

# 052 container file system

just made a file in one container and checked it the other container had that file it does not

```sh

```

# 053 persisting data using volumes

create volume

```sh
docker volume create <volume name>
```

inspect volume

```sh
docker volume inspect <volume name>
```

# 054 copying file between the host and container

this is how you copy a file from the container to the host

```sh
docker cp <container name>:<container file location> <host file location>
```

copy a file from the host to the container

```sh
docker cp <host file locaton> <container name>:<container file location>
```

# 055 shring the source code with container

this maps the rection5-react-app to the container /app

```sh
docker run -d -p 5001:3000 -v $(pwd):/app --name react-test react-app
```

Error: EACCES: permission denied, scandir '/app'

it worked with this as the dockerfile

<!-- Dockerfile
FROM node:14.16.0-alpine3.13
# RUN addgroup app && adduser -S -G app app
# USER app
WORKDIR /app
# COPY --chown=app package.json .
COPY package.json .
USER root
RUN mkdir data
RUN npm install
# USER app
# COPY --chown=app . .
COPY . .
ENV API_URL=http://api.myapp.com/
EXPOSE 3000
CMD ["npm", "start"] -->

this here on the top

> react-app@0.1.0 start /app
> react-scripts start

<!-- npm ERR! code ELIFECYCLE
npm ERR! syscall spawn sh
npm ERR! file sh
npm ERR! path sh
npm ERR! errno -13
npm ERR! react-app@0.1.0 start: `react-scripts start`
npm ERR! spawn sh EACCES
npm ERR!
npm ERR! Failed at the react-app@0.1.0 start script.
npm ERR! This is probably not a problem with npm. There is likely additional logging output above.

npm ERR! A complete log of this run can be found in:
npm ERR! /home/app/.npm/\_logs/2024-08-01T16_08_14_843Z-debug.log -->

sveltekit
docker run -d -p 3000:3000 --name svelte-test svelte-app

vvvvvvvvvvvvvsvelte.config.js vvvvvvvvvvvvvvv
import adapter from "@sveltejs/adapter-node";

vvvvvvvvvvvvvvite.config.js vvvvvvvvvvvvvvv
server: { port: 3000 },

<!-- # Create a node base image running node 16.14.0 on Alpine linux version 3.15
# FROM node:16.14.0-alpine3.15
# RUN addgroup app && adduser -S -G app app
# RUN mkdir /app && chown app:app /app
# USER app
# WORKDIR /app
# # COPY --chown=app package.json .
# RUN npm install
# COPY . .
# ENV API_URL=http://api.myapp.com
# EXPOSE 3000
# CMD ["npm", "start"] -->

# 056

docker compose
docker networking
database migration
running automated test

```sh

```

# 057

```sh

```

# 058

remove all containers

```sh
docker container rm -f $(docker container ls -aq)
```

remove all images

```sh
docker image rm $(docker image ls -q)
```

# 059

```sh

```

# 060

```sh

```

# 061

```sh

```

# 062

```sh

```

# 063

```sh

```

# 064

```sh

```

# 065

```sh

```

# 066

```sh

```

# 067

```sh

```

# 068

```sh

```

# 069

```sh

```

# 070

```sh

```

# 071

```sh

```

# 072

```sh

```

# 073

```sh

```

# 074

```sh

```

# 075

```sh

```

# 076

```sh

```

# 077

```sh

```

# 078

```sh

```

# 079

```sh

```
