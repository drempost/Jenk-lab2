pipeline {
  agent any
  
  stages {
    stage ('CloneGit') {
      steps {
        git url: 'https://github.com/jenkinsgituser/hello-world-war.git';
      }
    }
    stage ('Build') {
      steps {
        sh 'mvn clean install'
      }
    }
    stage ('Deploy - Staging'){   
      when {
        expression {
          currentBuild.result == null || currentBuild.result == 'Success'
        }
      }
      steps {
        echo 'OK' 
      }
    }
  }
}
