pipeline {
  agent any
  stages {
    stage('Build') {
      parallel {
        stage('Build') {
          steps {
            echo 'Running build automation'
            sh './gradlew build --no-daemon'
            archiveArtifacts 'dist/trainSchedule.zip'
          }
        }

        stage('test') {
          steps {
            fileExists 'TrainSchedule.zip'
          }
        }

      }
    }

  }
}