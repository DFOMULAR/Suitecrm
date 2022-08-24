# suitecrm-k8s

## 1. :notebook: Getting started

## 1.1 :pencil: Import SuiteCRM source

## 1.2 :cd: Run the SuiteCRM container locally

- First, pull the container image from docker hub, 

```bash 
docker pull jomoflash/suitecrm:v1.0
```

- Then start the contianer

```bash
docker run -d --name=my-suitecrm -p 3000:80  jomoflash/suitecrm:v1.0
```

- Open your web browser and access the application on `http://localhost:3000`

:pushpin: Note : it is required to have MySql database running either locally or remote for the setup and installation of the suitecrm instance

---

## 2. :wink: Run locally with docker-compose

to build
```
docker-compose build
```
```
docker-compose up -d 
```

- combine the two commands above

```
docker-compose up -d --build
```

---

## 3. :rocket: Doploying suitecrm to k8s 