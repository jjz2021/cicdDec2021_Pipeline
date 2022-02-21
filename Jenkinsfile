pipeline {
  agent any
  stages {
    stage('Git SCM ') {
      steps {
        git(url: 'https://github.com/jjz2021/cicdDec2021_Pipeline.git', branch: 'mait', changelog: true, poll: true)
        sleep 3
      }
    }

    stage('CompileCode') {
      steps {
        sh 'mvn compile'
      }
    }

    stage('testing') {
      parallel {
        stage('testing') {
          steps {
            sh 'mvn test'
          }
        }

        stage('testing2') {
          steps {
            echo 'This is testing 2'
          }
        }

      }
    }

    stage('Package') {
      steps {
        sh 'mvn package'
      }
    }

    stage('Execute') {
      steps {
        echo 'Run Jar file here'
      }
    }

  }
}
