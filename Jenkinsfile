pipeline {
  agent any
  stages {
    stage('Say Hello') {
      parallel {
        stage('Say Hello') {
          steps {
            sh 'echo "Hello From Neethu"'
          }
        }

        stage('Build gradle app') {
          agent {
            docker {
              image 'gradle:jdk11'
            }

          }
          steps {
            sh '''echo "HI"
sudo su -
./ ci/build-app.sh'''
          }
        }

      }
    }

  }
}