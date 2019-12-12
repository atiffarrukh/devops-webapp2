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

    stage('Publish') {
      steps {
        archiveArtifacts(artifacts: 'build/libs/*.war', fingerprint: true, onlyIfSuccessful: true)
      }
    }

  }
}
