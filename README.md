# UniqueBibleApp-alpine
Unique Bible App docker image built with Alpine Linux webtop

# About Unique Bible App
https://github.com/eliranwong/UniqueBible

# About Webtops
https://www.linuxserver.io/blog/2021-05-05-meet-webtops-a-linux-desktop-environment-in-your-browser

# For end-users

With <a href="https://www.docker.com">docker</a> installed first, run:

> sudo docker run -d --name=uniquebibleapp --security-opt seccomp=unconfined -e GUIAUTOSTART=true -e PUID=1000 -e PGID=1000 -e TZ=Europe/London -e SUBFOLDER=/ -e KEYBOARD=en-gb-qwerty -p 3000:3000 -v ~/uniquebibleapp-alpine:/config -v /var/run/docker.sock:/var/run/docker.sock --shm-size="1gb" --restart unless-stopped uniquebibleapp-alpine

# For developers

To build a docker image

> docker build -t uniquebibleapp-alpine .
