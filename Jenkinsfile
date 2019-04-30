node('linux'){
  stage('UnitTests'){
    git 'https://github.com/Joeshen32/java-project.git'
    sh 'ant -f test.xml -v'
    junit 'reports/result.xml'
  }
  
  stage('Build'){
    sh 'ant -f build.xml -v'
  }

  stage('Deploy'){
    sh 'aws s3 cp rectangle-*.jar s3://seis665-hw10-joeshen'
  }
  
  stage('Report'){
    sh 'aws cloudformation describe-stack-resources --region us-east-1 --stack-name jenkins'
  }
}

