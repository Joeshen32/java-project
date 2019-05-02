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
    sh 'aws s3 cp $WORKSPACE/dist/*.jar s3://seis665-hw10-joeshen/rectangle-${BUILD_NUMBER}.jar'
  }
  
  stage('Report'){
    withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: '77f4553d-4664-4247-a422-e7581d46a08f', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
    // some block
      sh 'aws cloudformation describe-stack-resources --region us-east-1 --stack-name jenkins'
    }

     
  }
}

