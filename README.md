## 👋 Welcome to tududi 🚀  

tududi README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update tududi
```
  
## Install and run container
  
```shell
mkdir -p "$HOME/.local/share/srv/docker/tududi/rootfs"
git clone "https://github.com/dockermgr/tududi" "$HOME/.local/share/CasjaysDev/dockermgr/tududi"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/tududi/rootfs/." "$HOME/.local/share/srv/docker/tududi/rootfs/"
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-tududi \
--hostname tududi \
-e TZ=${TIMEZONE:-America/New_York} \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-tududi/rootfs/data:/data:z" \
-v "$HOME/.local/share/srv/docker/casjaysdevdocker-tududi/rootfs/config:/config:z" \
-p 80:80 \
casjaysdevdocker/tududi:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdevdocker/tududi
    container_name: casjaysdevdocker-tududi
    environment:
      - TZ=America/New_York
      - HOSTNAME=tududi
    volumes:
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-tududi/rootfs/data:/data:z"
      - "$HOME/.local/share/srv/docker/casjaysdevdocker-tududi/rootfs/config:/config:z"
    ports:
      - 80:80
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdevdocker/tududi
```
  
OR
  
```shell
git clone "https://github.com/casjaysdevdocker/tududi" "$HOME/Projects/github/casjaysdevdocker/tududi"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdevdocker/tududi"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdevdocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/u/casjaysdevdocker) ⛵  
