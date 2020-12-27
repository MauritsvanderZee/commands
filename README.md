# List of useful commands
This repository is a collection of useful commands. It is by no means complete and will be extended as I continue my journey as software developer.

#### Docker

Setup docker container with mysql:
```
docker run -e MYSQL_ROOT_PASSWORD=root -d -p "3306:3306" --restart=always mysql:5.7
```

Setup docker container with keycloak:
```
docker run -p 8080:8080 -e KEYCLOAK_USER=admin -e KEYCLOAK_PASSWORD=admin quay.io/keycloak/keycloak:12.0.1
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

#### Renew [letsencrypt](https://letsencrypt.org/) certificats

```
$ systemctl stop nginx
$ certbot renew
$ systemctl start nginx
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

### Latex

Convert a file to pdf with inkscape:

```
inkscape -D -z --file=image.svg --export-pdf=image.pdf --export-latex
```

### GPG Keys for GitHub

```
# Generate new key, set your email you are using with your GitHub account
$ gpg --gen-key

# List all your local keys
$ gpg --list-secret-keys --keyid-format LONG

# Set key in local git config
$ git config --global user.signingkey XXXXXXXXXXXXXXXX

# Enable git signing
$ git config --global commit.gpgsign true

# Set config that password will not be asked everytime a commit is performed
$ sudo nano ~/.gnupg/gpg-agent.conf

# Add line for mac:
pinentry-program /usr/local/bin/pinentry-mac

#Add line for Linux
pinentry-program /usr/bin/pinentry-qt

# Export your key for GitHub
$ gpg --armor --export XXXXXXXXXXXXXXXX > key.txt

# Copy the key from the file to your GitHub settings
```
