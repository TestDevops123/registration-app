pipeline{
 agent{label 'Jenkins-agent'}
 tools{
   jdk 'Java17'
   maven 'Maven3'
 }
  
  stages{
  stage("Cleanup workspace"){
    steps{
      CleanWs()
    }
  }
    stage ("Checkout fom SCM"){
      steps {
git branch: 'main', url: 'https://github.com/TestDevops123/registration-app'
      }
    }
       stage ("Build application"){
      steps {
sh 'mvn clean package'
      }
    }
    stage("Test application"){
      steps{
   sh 'mvn test'
    }
  }
       
      }
