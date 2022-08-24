# suitecrm-k8s

## 1. :notebook: Getting started

Visit [this](https://suitecrm.com/download/) page to get the latest version of SuiteCRM, This project setup uses version 7.x, copy the download link of the file and use `wget [link]` as described in the next section to download the application setup file.

:pushpin: Note: Any other major version may fail with this setup, to use version 8.x, update the php version in the Dockerfile to meet with requirement specified.

### 1.1 :pencil: Import SuiteCRM source
```bash
wget https://suitecrm.com/files/147/SuiteCRM-7.12/630/SuiteCRM-7.12.7.zip
```
```bash
unzip SuiteCRM-7.12.7.zip -q
```
```bash
cp -r SuiteCRM-7.12.7/* suitecrm-k8s/suitecrm_source/public/
```

### 1.2 :wink: Build and Run with docker-compose

to build
- `docker-compose build`

- `docker-compose up -d`

combine the two commands above

```
docker-compose up -d --build
```
- :fire: To tear down everything :exclamation:
```bash
docker-compose down -v
```

---
## 2 :cd: Run the SuiteCRM container locally using already built image

- First, pull the container image from docker hub, 

```bash 
docker pull jomoflash/suitecrm:v1.0
```

- Then start the contianer

```bash
docker run -d --name=my-suitecrm -p 3000:80  jomoflash/suitecrm:v1.0
```

- Open your web browser and access the application on `http://localhost:3000`

:pushpin: Note: it is required to have MySql database running either locally or remote for the setup and installation of the suitecrm instance

---

## 3. :rocket: Doploying suitecrm to k8s 