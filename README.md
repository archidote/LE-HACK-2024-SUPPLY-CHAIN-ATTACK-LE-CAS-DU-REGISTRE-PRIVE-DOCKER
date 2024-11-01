# SUPPLY CHAIN ATTACK : LE CAS DU REGISTRE PRIVÉ DOCKER (Conférence - [leHACK](https://x.com/_lehack_?lang=en) 2024)

Le *repository* github contient les éléments suivants : 

## CFP (Call For Paper)
- CFP-Supply-Chain-Attack-Le-Cas Du-Registre-Privé-Docker.pdf (Original)
- https://lehack.org/track/supply-chain-attack-le-cas-du-registre-prive-docker/
  
## Support de présentation 
- Supply-Chain-Attack-Le-Cas-Du-Registre-Privé-Docker-LE-HACK-2024.pdf
## Article du magazine MISC n°134 Juillet/Août 2024
- https://boutique.ed-diamond.com/en-kiosque/1690-misc-134.html

## Replay de la conférence 

- https://youtu.be/f8t-z0M9C-k?si=zKvSUj5g-ebCrG_0

## Annexes
### Image Docker utilisés pour la démonstration : 

- gitalpha : https://hub.docker.com/repository/docker/archidote/gitalpha/general
- mywebapp : https://hub.docker.com/repository/docker/archidote/mywebapp/general
### docker-compose.yml pour recréer le conteneur watchtower : 

```
version: "3"
services:
  one:
    image: 192.168.130.133:5000/mywebapp:latest
    ports:
      - "80:80"
    restart: always
  watchtower:
    image: containrrr/watchtower
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
    command: --interval 10
```
