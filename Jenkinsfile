pipeline {
  agent any
  stages {
    stage('Upload to AWS') {
      steps {
        withAWS(region:'us-west-2',accessKeyVariable: 'AWS_ACCESS_KEY_ID', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY') {
          s3Delete(bucket: 'tirgan-jenkins-website', path:'**/*.html')
          s3Upload(bucket: 'tirgan-jenkins-website', workingDir:'build', includePathPattern:'**/*.html');
        }
      }
    }
  }
}
