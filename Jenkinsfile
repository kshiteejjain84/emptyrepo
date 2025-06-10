pipeline {
  agent any
  stages {
    stage('creating docker volume') {
      steps {
        sh 'docker volume create server'
        sh ' cd /var/lib/docker/volumes/server/_data'
        sh 'echo "hello welcome to docker" >> index.html'
      }
    }
    stage('creatin & login to container and attaching volume to it') {
      steps {
        sh 'docker run -dp 80:80 -v server:/usr/local/apache2/htdocs --name httpd1 httpd'
      }
    }
  }
}
