# repositoriopublicoSRI-5
## DNS
## Configura un contenedor coa imaxe oficial de bind9 usando docker-compose.

### Crear carpeta bind 9 y fichero docker compose
mkdir bind9-docker

touch docker-compose.yml




### Configuracion fichero docker compose
-- >Primero para entrar lo que hice fue entrar con nano docker-compose.yml en el archivo y ponerle lo siguiente:

version: '3.8' 

services: 
  bind9:
    image: internetsystemsconsortium/bind9:9.18
    container_name: bind9

    ports: 
      - "53:53/tcp"
      - "53:53/udp"

    volumes: 
      - ./named.conf.options:/etc/bind/named.conf.options
      - ./zones:/etc/bind/zones
      - ./logs:/var/log/bind

    restart: unless-stoppedsudo>
    
    
  Para comprobar que se hizo bien y va bien   *docker-compose up -d*

### - SUbir todo a Git

git init
git add docker-compose.yml 
git commit


git remote add origin https://github.com/oscardieste/bind9-docker-setup.git

git push -u origin master

    


