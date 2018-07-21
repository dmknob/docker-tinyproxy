Tinyproxy for Docker
====================
## Simplest dockerized Tinyproxy.
### Runs over lastest Alpine image (lightweight, ˜4.54MB with alpine 3.8)

- Clone Repo

> git clone https://github.com/dmknob/docker-tinyproxy.git

- BUILD
> cd docker-tinyproxy
> sudo docker build -t tinyproxy .

- RUN on port 8118
> sudo docker run -d --rm --name='tinyproxy' -p 8118:8888 tinyproxy

- RUN with other tinyproxy.conf.
 Usefull when you want to define who can access the proxy.
 You can just append an Allow directive at the end of a copy of tinyproxy.conf
 ex:  Allow 123.45.67.89
> sudo docker run -d --rm --name='tinyproxy' -p 8118:8888 -v "/home/user/tinyproxy.conf:/etc/tinyproxy/tinyproxy.conf:ro" tinyproxy
