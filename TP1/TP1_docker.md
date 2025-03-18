# TP1 : Containers
# Part I : Docker basics
🌞 Installer Docker votre machine Azure
- Installation Docker
~~~
for pkg in docker.io docker-doc docker-compose docker-compose-v2 podman-docker containerd runc; do sudo apt-get remove $pkg; done

sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin

azureuser@doigVM:~$ sudo docker run hello-world
Unable to find image 'hello-world:latest' locally
latest: Pulling from library/hello-world
e6590344b1a5: Pull complete
Digest: sha256:7e1a4e2d11e2ac7a8c3f768d4166c2defeb09d2a750b010412b6ea13de1efb19
Status: Downloaded newer image for hello-world:latest

Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
 ~~~

 - démarrage docker

 ~~~
 azureuser@doigVM:~$ sudo systemctl status docker
● docker.service - Docker Application Container Engine
     Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)
     Active: active (running) since Fri 2025-03-14 10:15:05 UTC; 4min 32s ago
TriggeredBy: ● docker.socket
       Docs: https://docs.docker.com
   Main PID: 2246 (dockerd)
      Tasks: 9
     Memory: 103.9M
        CPU: 442ms
     CGroup: /system.slice/docker.service
             └─2246 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock
~~~

- ajout utilisateur au docker

~~~
sudo usermod -aG docker $(whoami)
~~~

🌞 Utiliser la commande `docker run`

~~~
azureuser@doigVM:~$ docker run --name web -d -v /path/to/html:/usr/share/nginx/html -p 9999:80 nginx
Unable to find image 'nginx:latest' locally
latest: Pulling from library/nginx
7cf63256a31a: Pull complete
bf9acace214a: Pull complete
513c3649bb14: Pull complete
d014f92d532d: Pull complete
9dd21ad5a4a6: Pull complete
943ea0f0c2e4: Pull complete
103f50cb3e9f: Pull complete
Digest: sha256:9d6b58feebd2dbd3c56ab5853333d627cc6e281011cfd6050fa4bcf2072c9496
Status: Downloaded newer image for nginx:latest
6d3daecf0dfb0985c765f4916c3fef8a82c95e0e893b173898b7327ca79198ea
~~~

🌞 Rendre le service dispo sur internet

~~~
azureuser@doigVM:~$ curl 40.81.232.1
<!DOCTYPE html>
<html>
<head>
<title>Welcome to nginx!</title>
<style>
    body {
        width: 35em;
        margin: 0 auto;
        font-family: Tahoma, Verdana, Arial, sans-serif;
    }
</style>
</head>
<body>
<h1>Welcome to nginx!</h1>
<p>If you see this page, the nginx web server is successfully installed and
working. Further configuration is required.</p>

<p>For online documentation and support please refer to
<a href="http://nginx.org/">nginx.org</a>.<br/>
Commercial support is available at
<a href="http://nginx.com/">nginx.com</a>.</p>

<p><em>Thank you for using nginx.</em></p>
</body>
</html>
~~~

🌞 Custom un peu le lancement du conteneur

~~~
azureuser@doigVM:~$ sudo nano /etc/nginx/toto.conf

server {
  # on définit le port où NGINX écoute dans le conteneur
  listen 7777;
  
  # on définit le chemin vers la racine web
  # dans ce dossier doit se trouver un fichier index.html
  root /var/www/tp_docker; 
}
~~~

~~~
sudo nano /etc/nginx/index.html
~~~

~~~
azureuser@doigVM:~$ docker run -d --name meow -v $(pwd)/toto.conf:/etc/nginx/conf.d/toto.conf -v $(pwd)/index.html:/var/www/tp_docker/index.html -p 7777:7777 --memory=512m nginx:latest
~~~
# Part II : Images
- Construisez votre propre Dockerfile
🌞 Construire votre propre image
- création `Dockerfile`
~~~
azureuser@PCMaisonTP1:/etc/Partie2$ sudo nano Dockerfile
azureuser@PCMaisonTP1:/etc/Partie2$ sudo cat Dockerfile
FROM ubuntu

RUN apt update -y

RUN apt install -y apache2

COPY apache2.conf /etc/apache2/apache2.conf

COPY index.html /var/www/html/index.html

CMD ["apache2", "-DFOREGROUND"]
~~~
- création conf `apache2`
~~~
azureuser@PCMaisonTP1:/etc/Partie2$ sudo nano apache2.conf
azureuser@PCMaisonTP1:/etc/Partie2$ sudo cat apache2.conf
# Définir un port sur lequel écouter
Listen 80

# Charger les modules Apache nécessaires
LoadModule mpm_event_module "/usr/lib/apache2/modules/mod_mpm_event.so"
LoadModule dir_module "/usr/lib/apache2/modules/mod_dir.so"
LoadModule authz_core_module "/usr/lib/apache2/modules/mod_authz_core.so"

# Spécifier le fichier HTML par défaut
DirectoryIndex index.html

# Définir le répertoire de travail du site
DocumentRoot "/var/www/html/"

# Paramètres pour les logs
ErrorLog "logs/error.log"
LogLevel warn
~~~
- création fichier `html`
~~~
azureuser@PCMaisonTP1:/etc/Partie2$ sudo nano index.html
azureuser@PCMaisonTP1:/etc/Partie2$ sudo cat index.html
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <title>Ma page d'accueil Apache</title>
</head>
<body>
    <h1>Salut, voici ma page d'accueil personnalisée !</h1>
    <p>Bienvenue sur mon serveur Apache personnalisé !</p>
</body>
</html>
~~~
# Part III : docker-compose
🌞 Installez un WikiJS en utilisant Docker
~~~
azureuser@PCMaisonTP1:/etc/Partie3/wiki$ cat docker-compose.yaml
version: "3"
services:

  db:
    image: postgres:15-alpine
    environment:
      POSTGRES_DB: wiki
      POSTGRES_PASSWORD: wikijsrocks
      POSTGRES_USER: wikijs
    logging:
      driver: "none"
    restart: unless-stopped
    volumes:
      - db-data:/var/lib/postgresql/data

  wiki:
    image: ghcr.io/requarks/wiki:2
    depends_on:
      - db
    environment:
      DB_TYPE: postgres
      DB_HOST: db
      DB_PORT: 5432
      DB_USER: wikijs
      DB_PASS: wikijsrocks
      DB_NAME: wiki
    restart: unless-stopped
    ports:
      - "8888:80"

volumes:
  db-data:


docker compose up -d 
~~~
🌞 Création image python3
- `Dockerfile`
~~~
Dockerfile
FROM python:3.9

WORKDIR /app

COPY . /app

RUN pip install --no-cache-dir -r requirements.txt

EXPOSE 8888

CMD ["python","app.py"]
~~~
- `docker-compose.yaml`
~~~
docker-compose.yaml
version: '3.8'

services:
  app:
    build: .
    ports:
      - "8888:8888"
    depends_on:
      - db
    environment:
      - REDIS_HOST=db
      - REDIS_PORT=6379

  db:
    image: "redis:alpine"
    ports:
~~~
# Part IV : Docker security
🌞 Prouvez que vous pouvez devenir root
~~~
azureuser@PCMaisonTP1:/etc/Partie3/app$ docker run -it -v /etc/shadow:/etc/shadow alpine sh
Unable to find image 'alpine:latest' locally
latest: Pulling from library/alpine
f18232174bc9: Already exists
Digest: sha256:a83b36e8b8210634f77d9f7f9acf7dfa463e380b75e2e74aff4511df3ef88c
Status: Downloaded newer image for alpine:latest
/ # cat /etc/shadow
root:*:20140:0:99999:7:::
daemon:*:20140:0:99999:7:::
bin:*:20140:0:99999:7:::
sys:*:20140:0:99999:7:::
sync:*:20140:0:99999:7:::
~~~
🌞 Utilisez Trivy
~~~
azureuser@PCMaisonTP1:~$ trivy image --security-checks vuln ghcr.io/requarks/wiki
2025-03-14T19:00:52Z    WARN    '--security-checks' is deprecated. Use '--scanners' instead.
2025-03-14T19:00:52Z    INFO    [vulndb] Need to update DB
2025-03-14T19:00:52Z    INFO    [vulndb] Downloading vulnerability DB...
2025-03-14T19:00:52Z    INFO    [vulndb] Downloading artifact...        repo="mirror.gcr.io/aquasec/trivy-db:2"
60.87 MiB / 60.87 MiB [-----------------------------------------------------------------------] 100.00% 4.38 MiB p/s 14s
2025-03-14T19:01:06Z    INFO    [vulndb] Artifact successfully downloaded       repo="mirror.gcr.io/aquasec/trivy-db:2"
2025-03-14T19:01:06Z    INFO    [vuln] Vulnerability scanning is enabled
2025-03-14T19:01:25Z    INFO    Detected OS     family="alpine" version="3.21.2"
2025-03-14T19:01:25Z    INFO    [alpine] Detecting vulnerabilities...   os_version="3.21" repository="3.21" pkg_num=71
2025-03-14T19:01:25Z    INFO    Number of language-specific files       num=1
2025-03-14T19:01:25Z    INFO    [node-pkg] Detecting vulnerabilities...
2025-03-14T19:01:26Z    WARN    Using severities from other vendors for some vulnerabilities. Read https://trivy.dev/v0.60/docs/scanner/vulnerability#severity-selection for details.
2025-03-14T19:01:26Z    INFO    Table result includes only package filenames. Use '--format json' option to get the full path to the package file.

Report Summary

┌──────────────────────────────────────────────────────────────────────────────────┬──────────┬─────────────────┐
│                                      Target                                      │   Type   │ Vulnerabilities │
├──────────────────────────────────────────────────────────────────────────────────┼──────────┼─────────────────┤
│ ghcr.io/requarks/wiki (alpine 3.21.2)                                            │  alpine  │       27        │


azureuser@PCMaisonTP1:~$ trivy image --security-checks vuln postgres
2025-03-14T19:03:26Z    WARN    '--security-checks' is deprecated. Use '--scanners' instead.
2025-03-14T19:03:26Z    INFO    [vuln] Vulnerability scanning is enabled
2025-03-14T19:03:32Z    INFO    Detected OS     family="debian" version="12.9"
2025-03-14T19:03:32Z    INFO    [debian] Detecting vulnerabilities...   os_version="12" pkg_num=147
2025-03-14T19:03:32Z    INFO    Number of language-specific files       num=1
2025-03-14T19:03:32Z    INFO    [gobinary] Detecting vulnerabilities...
2025-03-14T19:03:32Z    WARN    Using severities from other vendors for some vulnerabilities. Read https://trivy.dev/v0.60/docs/scanner/vulnerability#severity-selection for details.

Report Summary

┌────────────────────────┬──────────┬─────────────────┐
│         Target         │   Type   │ Vulnerabilities │
├────────────────────────┼──────────┼─────────────────┤
│ postgres (debian 12.9) │  debian  │       152       │
├────────────────────────┼──────────┼─────────────────┤
│ usr/local/bin/gosu     │ gobinary │       58        │
└────────────────────────┴──────────┴─────────────────┘


azureuser@PCMaisonTP1:~$ trivy image --security-checks vuln apache-alpine
2025-03-14T19:04:16Z    WARN    '--security-checks' is deprecated. Use '--scanners' instead.
2025-03-14T19:04:16Z    INFO    [vuln] Vulnerability scanning is enabled
2025-03-14T19:04:17Z    INFO    Detected OS     family="alpine" version="3.21.3"
2025-03-14T19:04:17Z    INFO    [alpine] Detecting vulnerabilities...   os_version="3.21" repository="3.21" pkg_num=21
2025-03-14T19:04:17Z    INFO    Number of language-specific files       num=0

Report Summary

┌───────────────────────────────┬────────┬─────────────────┐
│            Target             │  Type  │ Vulnerabilities │
├───────────────────────────────┼────────┼─────────────────┤
│ apache-alpine (alpine 3.21.3) │ alpine │        0        │
└───────────────────────────────┴────────┴─────────────────┘


azureuser@PCMaisonTP1:~$ trivy image --security-checks vuln nginx:latest
2025-03-14T19:05:09Z    WARN    '--security-checks' is deprecated. Use '--scanners' instead.
2025-03-14T19:05:09Z    INFO    [vuln] Vulnerability scanning is enabled
2025-03-14T19:05:39Z    INFO    [javadb] Downloading Java DB...
2025-03-14T19:05:39Z    INFO    [javadb] Downloading artifact...        repo="mirror.gcr.io/aquasec/trivy-java-db:1"
697.86 MiB / 697.86 MiB [-----------------------------------------------------------------------------------------------------] 100.00% 8.68 MiB p/s 1m21s
2025-03-14T19:07:01Z    INFO    [javadb] Artifact successfully downloaded       repo="mirror.gcr.io/aquasec/trivy-java-db:1"
2025-03-14T19:07:01Z    INFO    [javadb] Java DB is cached for 3 days. If you want to update the database more frequently, "trivy clean --java-db" command clears the DB cache.
2025-03-14T19:07:01Z    INFO    Detected OS     family="debian" version="12.9"
2025-03-14T19:07:01Z    INFO    [debian] Detecting vulnerabilities...   os_version="12" pkg_num=149
2025-03-14T19:07:01Z    INFO    Number of language-specific files       num=0
2025-03-14T19:07:01Z    WARN    Using severities from other vendors for some vulnerabilities. Read https://trivy.dev/v0.60/docs/scanner/vulnerability#severity-selection for details.

Report Summary

┌────────────────────────────┬────────┬─────────────────┐
│           Target           │  Type  │ Vulnerabilities │
├────────────────────────────┼────────┼─────────────────┤
│ nginx:latest (debian 12.9) │ debian │       157       │
└────────────────────────────┴────────┴─────────────────┘
~~~