pipeline {
  agent {
    node {
      label 'host'
    }

  }
  stages {
    stage('clone') {
      steps {
        stash(name: 'code', excludes: '.git')
      }
    }

    stage('build app') {
      parallel {
        stage('build app') {
          steps {
            unstash 'code'
            sh 'sh ci/buid-app.sh'
          }
        }

        stage('say hello') {
          steps {
            sh 'sh \'echo "Hello from Neethu"\''
          }
        }

      }
    }

  }
}