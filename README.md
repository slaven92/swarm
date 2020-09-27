# Docker stacks for some of the most common apps

## App list
* pi-hole
* plex
* qbittorrent
* duckdns
* nextcloud
* portainer
* Monitoring apps:
  * prometheus
  * loki
  * nginx_exporter
  * promtail
  * grafana
  
  
- Make sure that you have docker installed and that you are in swarm mode (`docker swarm init`).
- Make folder for secrets, create and populate secretes that are necessery:
```bash
mkdir secrets
cd secrets/
touch duckdns_hostnames duckdns_token nextcloud_password nextcloud_user postgres_db postgres_password postgres_user
```

## Some notes on apps

### Pihole
No special notes. You can change pasword(`docker exec -it [pihole_container_name] pihole -a -p`) or get the random password from the logs(`docker logs pihole | grep random`)
I did not add password in the yaml file because I cannot use secrets.

### Nextcloud
I could not make it work with allowed domain env variable. I had to change the config.php file to add allowed domains.

Also you will have to add reverse proxy in from and add SSL certificate.
TODO explain nginx and certbot

### Duckdns
Add comma separated duckdns hosts.

### Portainer
I just copied the instructions from the portainer website.

TODO rest of the file
