pipeline {
  agent any
  stages {
    stage('creating docker volume') {
      steps {
        dir('/var/lib/docker/volumes/server/_data') {
        sh 'docker volume create server'
        sh 'echo "hello welcome to docker" >> index.html'
        }
        }
    }
    stage('creatin & login to container and attaching volume to it') {
      steps {
        sh 'docker run -dp 80:80 -v server:/usr/local/apache2/htdocs --name httpd1 httpd'
      }
    }
  }
}
