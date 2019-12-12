pipeline {
  agent {
    node {
      label 'master'
    }

  }
  stages {
    stage('Clone') {
      steps {
        git(url: 'https://github.com/atiffarrukh/devops-webapp2', branch: 'master')
      }
    }

    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            sh '''whoami
date
echo $PATH
echo "Atif"
pwd
ls -la
./gradlew build --info'''
          }
        }

        stage('parallel') {
          steps {
            sh '''echo "run parallel"
date'''
          }
        }

        stage('P2') {
          steps {
            sh 'echo "parallel 2"'
          }
        }

      }
    }

    stage('Publish') {
      steps {
        archiveArtifacts(artifacts: 'build/libs/*.war', fingerprint: true, onlyIfSuccessful: true)
      }
    }

  }
}