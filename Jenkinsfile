pipeline {
  agent any 
  stages {
    stage('build') {
      steps {
        sh '''
        aws ecr get-login-password --region us-west-1 | docker login --username AWS --password-stdin 421215178782.dkr.ecr.us-west-1.amazonaws.com
        docker build . -t 421215178782.dkr.ecr.us-west-1.amazonaws.com/nsa4e-dev:latest
        docker push 421215178782.dkr.ecr.us-west-1.amazonaws.com/nsa4e-dev:latest
        '''
      }
    }
  }
}
