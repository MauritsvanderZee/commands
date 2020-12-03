# commands
Repository with useful commands

#### Docker

Setup docker container with mysql:
```
docker run -e MYSQL_ROOT_PASSWORD=root -d -p "3306:3306" --restart=always mysql:5.7
```
#### destreamer

destreamer can be used to download videos from MS Teams / MS Streams.

```
./destreamer.sh -i "VIDEO_URL"
```
