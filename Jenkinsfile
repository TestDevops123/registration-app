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

 stage('Post-build Notifications') {
            steps {
                post {
                    failure {
                        mail to: 'dev-team@example.com',
                             subject: "Failed Build Notification: ${currentBuild.fullDisplayName}",
                             body: "The build failed at stage ${STAGE_NAME}. Check console output at ${BUILD_URL}."
                    }
                }
            }
        }
}
}
