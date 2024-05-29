## 👋 Welcome to almalinux 🚀  

almalinux README  
  
  
## Install my system scripts  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 sudo systemmgr --config && sudo systemmgr install scripts  
```
  
## Automatic install/update  
  
```shell
dockermgr update almalinux
```
  
## Install and run container
  
```shell
mkdir -p "$HOME/.local/share/srv/docker/almalinux/rootfs"
git clone "https://github.com/dockermgr/almalinux" "$HOME/.local/share/CasjaysDev/dockermgr/almalinux"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/almalinux/rootfs/." "$HOME/.local/share/srv/docker/almalinux/rootfs/"
docker run -d \
--restart always \
--privileged \
--name casjaysdev-almalinux \
--hostname almalinux \
-e TZ=${TIMEZONE:-America/New_York} \
casjaysdev/almalinux:latest
```
  
## via docker-compose  
  
```yaml
version: "2"
services:
  ProjectName:
    image: casjaysdev/almalinux
    container_name: casjaysdev-almalinux
    environment:
      - TZ=America/New_York
      - HOSTNAME=almalinux
    restart: always
```
  
## Get source files  
  
```shell
dockermgr download src casjaysdev/almalinux
```
  
OR
  
```shell
git clone "https://github.com/casjaysdev/almalinux" "$HOME/Projects/github/casjaysdev/almalinux"
```
  
## Build container  
  
```shell
cd "$HOME/Projects/github/casjaysdev/almalinux"
buildx 
```
  
## Authors  
  
🤖 casjay: [Github](https://github.com/casjay) 🤖  
⛵ casjaysdev: [Github](https://github.com/casjaysdev) [Docker](https://hub.docker.com/u/casjaysdev) ⛵  
