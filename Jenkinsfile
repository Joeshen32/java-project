pipeline {
  stages('Unit Tests'){
    sh 'ant'
    sh 'ant -f text.xml -v'
    sh 'reports/result.xml'
  }

}

