pipeline {
  agent any
  stages {
    stage('Upload to AWS') {
      steps {
        withAWS(region:'us-west-2', credentials: 'aws-static') {
          s3Delete(bucket: 'tirgan-jenkins-website', path:'**/*.html')
          s3Upload(file: 'index.html', bucket: 'tirgan-jenkins-website');
        }
      }
    stage('Lint HTML') {
      steps {
         sh 'tidy -q -e *.html'
      }
    }
  }
}
