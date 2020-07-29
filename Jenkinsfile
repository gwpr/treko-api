pipeline {
  agent {
    docker  {
      image "node:alpine"
      args "--network=skynet"
    }
  }
  stages {
    stage("Build") {
      steps {
        sh "echo 'http://dl-cdn.alpinelinux.org/alpine/v3.12/main' >> /etc/apk/repositories"
         sh "echo 'http://dl-cdn.alpinelinux.org/alpine/v3.12/community' >> /etc/apk/repositories"
         sh "apk update"
         sh "apk add mongodb=3.4.4-r0"
         sh "mongo --version"
         sh "chmod +x ./scripts/dropdb.sh"
         sh "npm install"
      }
    }
    stage("Test") {
      steps {
       sh "npm run test:ci"
      }
    }
}
}
