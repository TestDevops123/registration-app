pipeline{
agent any
 tools{
   jdk 'java17'
   maven 'maven3'
 }
  
  stages{
  stage("Cleanup workspace"){
    steps{
    cleanWs()
    }
  }
    stage ("Checkout fom SCM"){
      steps {
git branch: 'main', url: 'https://github.com/TestDevops123/registration-app'
      }
    }
       stage ("Build application"){
      steps {
sh 'mvn clean packge'
      }
    }
    stage("Test application"){
      steps{
   sh 'mvn test'
    }
  }
  }
post {
         failure {
            mail to: 'email@example.com',
                 subject: "Build Notification: ${currentBuild.fullDisplayName}",
                 body: "Check console output at ${env.BUILD_URL} to view build details."
        }
    }
 
}

