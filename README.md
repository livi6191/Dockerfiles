# Dockerfiles

This repo contains a number of the docker-compose files I created and use on my dockers servers.

**Traefik v2**

Traefik is a HTTP reverse proxy and load balancer that the majority of my containers sit behind, this also provides a widlcard Let's Encrypt SSL certificate for the containers that have web interfaces.

I also have some other services in my network behind traefik despite them being physical servers rather than docker containers, this allows for the same SSL and protection as the docker containers on those nodes.

Traefik also ties in with authelia to secure the subdomains I use with two factor authentication.

**Authelia**

Authelia is a log on proxy that provides two factor authentication.

I use this to protect all of my services that are exposed, it ties in with traefik to intercept and provide a 2FA prompt before allowing access to the service



**Heimdall**

Heimdall is an open source dashboard container, that I use to create my own personal dashboards for acessing services from one web browser tab

**Guacamole**

Guacamole is a remote access proxy that can cover ssh, VNC and RDP acess for remote servers.

I use this when I need to access servers in my network without the need to use a VPN, The version I use has DUO integration and authelica providing 2x 2 factor authentication.

**Uptime-Kuma**

Uptiume-kuma is a monitoring container that has a easy to use GUI and can do a number of monitoring such as DNS, HTTPS TCP etc and also can do a status page if needed, it can also tie into discord webhooks which Iuse for notifications.

**Wordpress**

No description needed here, The image I use for this is slightly different from the official one, it uses nginx and PHP 8.0 at the time of writing this. The docker-compse file also uses the latest version of mariadb
