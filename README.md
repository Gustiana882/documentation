# Cli Docker

## List Image
``` bash
docker image ls
```
### atau
```bash
docker images
```

## Download Image Docker
```bash
docker pull <nama image>
```

## Start image
docker run 'nama image' 'perintah'
```bash
docker run ubuntu bash -c echo "hello"
```
```bash
docker run -ti ubuntu bash
```
docker run 'nama image:version' 'perintah'
```bash
docker run ubuntu:14.04 bash -c "echo hello"
```
menambahkan nama container
```bash
docker run --name container1 ubuntu:14.04 bash -c "echo hello"
```
menjalankan container di baground dengan menambahkan -d
```bash
docker run -ti -d ubuntu bash
```
melihat log yang berjalan kontainer
```bash
docker attach <idimage>
```
membuat proses baru
```bash
docker exec -ti <id image> <perintah>
```
keluar container tanpa menghentikan proses
```bash
ctrl+p ctrl+q
```

## Stop Container
```bash
docker stop <id container>
```
```bash
docker kill <id Conatiner>
```

## Melihat Log Container
```bash
docker logs <id image>
```

## Melihat List Container Yang Berjalan
```bash
docker ps
```
melihat semua container yang stop
```bash
docker ps -a
```


## Hapus histori list container
```bash
docker rm <id container>
```
hapus semua
```bash
docker rm $(docker ps -aq)
```

## Menyimpan image
```bash
docker commit container1

```

## Merubah nama image
```bash
docker tag <idImage> <nama Image>
```

## Hapus Image
```bash
docker rmi <id image>
```

## Melihat perubahan image atau mengatur image
```bash
docker inspact <idImage>
```

## Membuka port image
8080 port yang akan di jalankan di luar kontainer
80 port yang akan dijalankan di dalam kontainer
```bash
docker run -d -p 8080:80 <nameimage>
```

## Melihat perubahan image atau mengatur image
```bash
docker inspact <idImage>
```

## melihat list network
type
none stop koneksi kedalam maupun ke luar kontainer
host semuaport bisa masuk ke kontainer
bridge membatasi port yang masuk
```bash
docker network ls
```

## Membuat network baru
```bash
docker network create <name>
```

## menambahkan network ke kontainer
```bash
docker run -ti --name server1 --net <nama network> ubuntu bash
```
--rm menghapus log (hanya untuk test tidak untuk production)
```bash
docker run -ti --rm --name server1 --net <nama network> ubuntu bash
```
## Melihat perubahan image atau mengatur image
```bash
docker inspact <idImage>
```

## Penyimpanan kontainer
presistent menyimpan data di local dan container, 
docker run -ti --rm -v 'folder local' : 'folder internal docker'  ubuntu bash
```bash
docker run -ti --rm -v /home/gustiana:/folder/set  ubuntu bash
```
efimeral menyimpan data hanya di container
```bash
docker run -ti --rm -v :/folder/set  ubuntu bash
```

## Menambah env
```bash
docker run <image> -e <variable env>='value'
```
```bash
docker run <image> -e <variable env>='value' -e <variable env>='value'
```

## Membuat image docker file
from memilih image
workdir membuat folder
copy menyalin file
run menjalankan perintah
expose membuka port

```bash
FROM node:14

WORKDIR /usr/src/app

COPY package.json ./

RUN npm install

COPY . .

EXPOSE 9000

CMD [ "node", "server.js" ]
```

dockerignore
```bash
.dockerignore
node_modules
```

## menjalankan file docker image
```bash
docker build -t <nama image> .
```

## Membuat image docker compose
from memilih image
workdir membuat folder
copy menyalin file
run menjalankan perintah
expose membuka port

```bash
FROM node:14

WORKDIR /usr/src/app

COPY package.json ./

RUN npm install

COPY . .

EXPOSE 9000

CMD [ "node", "server.js" ]
```

dockerignore
```bash
.dockerignore
node_modules
```

## menjalankan file docker image
```bash
docker build -t <nama image> .
```
