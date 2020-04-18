# Tarea # 7: Contenedores (2/2)

VIDEOS DEMO: 
PARTE 1: https://youtu.be/GOZSfHXiSfY
PARTE 2: https://youtu.be/J_Povx2e6fY

1. Instalamos Jenkins:  brew install jenkins-lts

2. Iniciamos Jenkins: brew services start jenkins-lts

3. docker network create jenkins

4. docker volume create jenkins-docker-certs
   docker volume create jenkins-data

5. docker container run --name jenkins-docker --rm --detach --privileged --network jenkins --network-alias docker --env DOCKER_TLS_CERTDIR=/certs --volume jenkins-docker-certs:/certs/client --volume jenkins-data:/var/jenkins_home --volume "$HOME":/home --publish 3000:3000 docker:dind

6. docker container run --name jenkins-tutorial --rm --detach --network jenkins --env DOCKER_HOST=tcp://docker:2376 --env DOCKER_CERT_PATH=/certs/client --env DOCKER_TLS_VERIFY=1 --volume jenkins-data:/var/jenkins_home --volume jenkins-docker-certs:/certs/client:ro --volume "$HOME":/home --publish 8080:8080 jenkinsci/blueocean

7. docker container exec -it jenkins-tutorial bash  
8. docker container exec -it jenkins-tutorial bash

9. Ingresamos a http://localhost:8080
10. En otra terminal: docker logs jenkins-tutorial
11. Nos genera la clave:

Please use the following password to proceed to installation:

7f5d1fa24cbd468e8a911b3a9a4f0102

12. Nos aparece la bienvenida a jenkins y le damos: Install suggested plugins.
13. creamos el user Admin:  re4lawliet,01123581321fish, nueva: 8a2e48c6547aa14074e5f1549f7832d4044dc14e
14. Para detener el contenedor: docker container stop jenkins jenkins-docker
15. Clonamos el ejemplo de react en nuestro propio github 
16. Crear projecto de Pipeline
17. y en la parte de pipeline agregamos nuestro repositorio y guardamos Y ponemos bien la path del Jenkisfile sino no jala
18. luego iniciamos el Job den Ocean





fuente: https://jenkins.io/doc/tutorials/build-a-node-js-and-react-app-with-npm/#fork-sample-repository



