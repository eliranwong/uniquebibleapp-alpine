# UniqueBibleApp-alpine
Unique Bible App desktop version runs with Alpine webtop

With this package, you can now run Unique Bible App full desktop version in Windows / macOS / ChromeOS / Linux easily with a web browser.

# About Unique Bible App
https://github.com/eliranwong/UniqueBible

# About Webtops
https://www.linuxserver.io/blog/2021-05-05-meet-webtops-a-linux-desktop-environment-in-your-browser

# Install Docker FIRST

You can install docker on Windows, macOS, Linux, ChromeOS.

You may check our notes about docker setup at: https://github.com/eliranwong/ArchLinuxWebtop#setup-docker

# For end-users

With <a href="https://www.docker.com">docker</a> installed FIRST, run:

Use either one of the following, depending on your OS:

For macOS Users:

> docker run -d --name=uniquebibleapp --security-opt seccomp=unconfined -e GUIAUTOSTART=true -e PUID=501 -e PGID=20 -e TZ=Europe/London -e SUBFOLDER=/ -e KEYBOARD=en-gb-qwerty -p 3000:3000 -v ~/uniquebibleapp-alpine:/config -v /var/run/docker.sock:/var/run/docker.sock -v ~/.config/pulse:/config/.config/pulse --shm-size="1gb" --restart unless-stopped eliranwong/uniquebibleapp

For other OS Users:

> sudo docker run -d --name=uniquebibleapp --security-opt seccomp=unconfined -e GUIAUTOSTART=true -e PUID=1000 -e PGID=1000 -e TZ=Europe/London -e SUBFOLDER=/ -e KEYBOARD=en-gb-qwerty -p 3000:3000 -v ~/uniquebibleapp-alpine:/config -v /var/run/docker.sock:/var/run/docker.sock --shm-size="1gb" --restart unless-stopped eliranwong/uniquebibleapp

Notes:

1) Check host user id, by running the following command and change "-e PUID=1000 -e PGID=1000" if applicable

> id [username]

2) "~/uniquebibleapp-alpine" is the local path for storing webtop home directory.  You may change to suit your own needs. 

# To run Unique Bible App

To run Unique Bible App, simple open "localhost:3000" in a web browser.

Running Unique Bible App the first time takes extra time before you can load "localhost:3000", as have a script to help you download and setup everything needed for running UniqueBible.app.  During the setup you may see a Terminal app opened and running the setup process.  Please expect to wait for at least 10 minutes for the setup.  This applies to the first run ONLY.  When the setup is finished, Unique Bible App will launch to fill up the web browser.  During the setup, please do not try to launch the app yourself, or it will cause extra delay.

# CLI command

You can simply launch Unique Bible App from a terminal app by running:

> uba

# Restart Unique Bible App

By default, Unique Bible App is automatically launched when you first log into the web interface via localhost:3000.  In case you close it and want to restart it, right click and select "Unique Bible App".

# Reload docker container

In case you want to reload the container, run in host terminal:

> docker restart uniquebibleapp

# Additional GUI apps

To facilitate the use of Unique Bible App, we also setup a few GUI apps, in addition to Unique Bible App, e.g.:

> thunar, ristretto, gnome-terminal, geany,vlc

You can launch these apps via command line tools or GUI menu with a right-click.

# For developers

To build a docker image from this repository:

> git clone https://github.com/eliranwong/uniquebibleapp-alpine.git

> cd uniquebibleapp-alpine

> docker build -t uniquebibleapp .

# For macOS users

To enable audio features, check https://github.com/eliranwong/ArchLinuxWebtop#setup-audio-macos-users-only
