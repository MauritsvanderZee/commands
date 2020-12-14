# List of useful commands
This repository is a collection of useful commands. It is by no means complete and will be extended as I continue my journey as software developer.

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

After download --> convert .mkv to .mp4 file

```
ffmpeg -i input.mkv -codec copy output.mp4
```

#### eruption (LED controller for keyboards)

```
$ paru -Sy aur/eruption-git
```

#### Compodoc
Issue with latest Angular versions in combination with electron:

```
cd <folder>
echo '{' > tsconfig.compodoc.json
echo '  "extends": "./tsconfig.json",' >> tsconfig.compodoc.json
echo '  "files": [' >> tsconfig.compodoc.json
for i in $(find src/ -name "*.ts")
do
   echo '    "'$i'",' >> tsconfig.compodoc.json
done
echo '  ],' >> tsconfig.compodoc.json
echo '}' >> tsconfig.compodoc.json
npx @compodoc/compodoc -p tsconfig.compodoc.json
```
[[Source]](https://github.com/compodoc/compodoc/issues/927#issuecomment-597624654)
