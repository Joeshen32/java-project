node('linux'){
  stage('UnitTests'){
    git 'https://github.com/Joeshen32/java-project.git'
    sh 'ant -f test.xml -v'
    sh 'reports/result.xml'
  }
  stage('Build'){
    sh 'ant -f build.xml -v'
  }

}

