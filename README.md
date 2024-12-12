# Hello Jenkins!

* Jenkins Installation by Docker

* Create a compose file `docker-compose.yml`

```
version: '3.8'

services:
  jenkins:
    image: jenkins/jenkins:lts
    container_name: jenkins
    ports:
      - "8080:8080"
      - "50000:50000"
    volumes:
      - jenkins-data:/var/jenkins_home
      - /var/run/docker.sock:/var/run/docker.sock

volumes:
  jenkins-data:

```

* Run Compose file `docker-compose up -d`
* Access Jenkins

```
http://<your-server-ip>:8080
```

* Retrieve the Jenkins initial admin password:

```
docker exec jenkins cat /var/jenkins_home/secrets/initialAdminPassword
```

* Complete the setup wizard:
  * Enter the password.
  * Install recommended plugins.
  * Set up the admin user and password.

