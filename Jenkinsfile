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
            sh './ ci/buildapp.sh'
          }
        }

      }
    }

  }
}