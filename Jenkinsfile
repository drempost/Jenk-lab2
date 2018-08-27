node {
  stage ('CloneGit') {
    git url: 'https://github.com/jenkinsgituser/hello-world-war.git';
  }
  stage ('Build') {
    sh 'mvn clean install'
  }
  stage ('Deploy - Staging'){
      
    when {
      expression {
        currentBuild.result == null || currentBuild.result == 'Success'
      }
    }
    echo 'OK' 
  }
}
