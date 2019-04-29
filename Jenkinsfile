pipeline {
  stages('Unit Tests'){
    git 'https://github.com/Joeshen32/java-project.git'
    sh 'ant -f text.xml -v'
    sh 'reports/result.xml'
  }

}

