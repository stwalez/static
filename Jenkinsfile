pipeline {
  agent any
  stages {
    stage('Upload to AWS') {
      steps {
        sh 'echo "Hello World" '
        sh '''
            echo "Multiline shell steps works too"
            ls -lah
         '''
        withAWS(region:'eu-west-1', credentials:'aws-static') { 
            s3Delete(bucket:'walejenkinstest', path:'/index.html')
            s3Upload(file:'index.html', bucket:'walejenkinstest', path:'index.html')
        }
        
      }
      
    }
  }
}
