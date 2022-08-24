# suitecrm-k8s
Doploying suitecrm to k8s 

Setup SuiteCRM docker container on Linux (Ubuntu)


1.  To install docker
visit https://docs.docker.com/engine/install/ then choose the environment to install docker on.
Linux, or Windows or MacOS through Docker Desktop.
Taking Ubuntu for instance: there are 3 installation options available:

1.Most users set up Docker’s repositories and install from them, for ease of installation and upgrade tasks. This is the recommended approach.

2.Some users download the DEB package and install it manually and manage upgrades completely manually.

3.In testing and development environments, some users choose to use automated convenience scripts to install Docker.

Proceeding with the third option here which is using a convenient script, run

$ curl -fsSL https://get.docker.com -o get-docker.sh
$ sudo sh get-docker.sh
To use Docker as a non-root user, you should consider adding your user to the “docker” group with something like:
  sudo usermod -aG docker <your-user>
Then relogin for this to take effect.
Now run  docker version  to confirm docker is successfully installed

2. Run the SuiteCRM container
First, pull the container image from docker hub, run $ docker pull jomoflash/suitecrm:v1.0
Then run $ docker run -d --name=my-suitecrm -p 3000:80  jomoflash/suitecrm:v1.0
Open your web browser and access the application on http://localhost:3000

Note : it is required to have MySql database running either locally or remote for the setup and installation of the suitecrm instance

