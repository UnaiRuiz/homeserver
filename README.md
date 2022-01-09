# HomeServer - Selfhosted Docker Services

## Table of Contents
 - [Deployment](#deployment)
 - [TODO](#todo)

## Deployment
1. Choose a random port for wireguard and config port forwarding on your router
2. Create directory tree for volumes
3. Fill .env-example with your values
4. Rename file:
```
mv .env-example .env
```
5. Create .env link in each subdirectory:
```
echo $HOME/homeserver/*/ | xargs -n 1 ln -s $HOME/homeserver/.env
```
6. Create proxy docker network
```
docker network create proxy
```
7. Exec services: (not tested)
```
echo $HOME/homeserver/*/ | xargs -d " " -I {} docker-compose -f {}/docker-compose.yml up -d
```
## TODO
- IMPROVE README.md
- Create a script to automate the entire deployment
- add more services
    - Authelia
    - ElasticSearch
    - ElastAlert
    - MinecraftServer
    - Grafana
    - Mosquitto
    - NodeRed
    - HomeAssistant
    - Joplin