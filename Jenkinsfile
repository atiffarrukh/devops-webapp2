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
            sh '''whoami
date
echo $PATH
echo "Atif 1"
pwd
ls -la
./gradlew build --info'''
          }
        }

        stage('P2') {
          steps {
            sh '''whoami
date
echo $PATH
echo "Atif 2"
pwd
ls -la
./gradlew build --info'''
          }
        }

        stage('P3') {
          steps {
            sh '''whoami
date
echo $PATH
echo "Atif 3"
pwd
ls -la
./gradlew build --info'''
          }
        }

        stage('P4') {
          steps {
            sh '''whoami
date
echo $PATH
echo "Atif 4"
pwd
ls -la
./gradlew build --info'''
          }
        }

        stage('P5') {
          steps {
            sh '''whoami
date
echo $PATH
echo "Atif 5"
pwd
ls -la
./gradlew build --info'''
          }
        }

        stage('P6') {
          steps {
            sh '''whoami
date
echo $PATH
echo "Atif 6"
pwd
ls -la
./gradlew build --info'''
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