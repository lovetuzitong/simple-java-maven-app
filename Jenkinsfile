pipeline {
  agent {
    docker {
      image 'maven:3-alpine'
      args '-v /root/.m2:/root/.m2'
    }

  }
  stages {
    stage('build') {
      parallel {
        stage('build') {
          steps {
            sh 'mvn -B -DskipTests clean package'
            echo 'hello multi steps'
          }
        }

        stage('build2') {
          steps {
            echo 'hello build 2'
          }
        }

        stage('build3') {
          steps {
            echo 'hello build 3'
          }
        }

      }
    }

    stage('test') {
      steps {
        sh 'mvn test'
      }
    }

  }
}