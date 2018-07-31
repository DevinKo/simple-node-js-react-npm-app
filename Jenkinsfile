pipeline {
  agent {
    docker {
      image 'node:6-alpine'
      args '-p 3000:3000'
    }

  }
  stages {
    stage('Build') {
      steps {
        sh '''docker run \\
  -u root \\
  --rm \\
  -d \\
  -p 8080:8080 \\
  -p 50000:50000 \\
  -v jenkins-data:/var/jenkins_home \\
  -v /var/run/docker.sock:/var/run/docker.sock \\
  jenkinsci/blueocean
'''
        sh 'npm install'
      }
    }
  }
}