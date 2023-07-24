# docker en jenkins

Dockerfile para instalar Docker dentro del contenedor de Jenkins

```
version: '3'
services:
  jenkins:
    user: root
    image: jenkins/docker
    build:
      context: dockerjenkins
    ports:
      - "8080:8080"
      - "50000:50000"
    container_name: jenkinsdocker
    volumes:
      - jenkins_home:/var/jenkins_home
      - /var/run/docker.sock:/var/run/docker.sock
    networks:
      - net
volumes:
  jenkins_home:
networks:
  net:
```
