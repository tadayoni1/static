pipeline {
  agent any
  stages {
    stage('Upload to AWS') {
      steps {
        withAWS(region:'us-west-2', credentials: 'aws-static') {
          s3Delete(bucket: 'tirgan-jenkins-website', path:'**/*.html')
          s3Upload(bucket: 'tirgan-jenkins-website', workingDir:'static', includePathPattern:'**/*.html');
        }
      }
    }
  }
}
