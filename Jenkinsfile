pipeline{
 agent{label 'Jenkins-agent'}
 tools{
   jdk 'java17'
   maven 'maven3'
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
}
