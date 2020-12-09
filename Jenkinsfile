pipeline {
  agent any
  stages {
    stage('Version Logging') {
      parallel {
        stage('Version Logging') {
          steps {
            sh '''java -version
mvn --version
git --version'''
          }
        }

        stage('POM Verification') {
          steps {
            sh 'dir'
            fileExists 'pom.xml'
          }
        }

      }
    }

    stage('Build') {
      steps {
        timeout(time: 500) {
          sh '''echo "Hello World"
mvn install'''
        }

        timestamps()
      }
    }

    stage('Conclusion') {
      steps {
        writeFile(file: 'conclusion.txt', text: 'We did it!')
      }
    }

  }
}