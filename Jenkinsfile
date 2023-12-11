pipeline {
  agent { label 'jenkins-Agent' }
  tools { 
      jdk 'java17'
      maven 'Maven3'
      }
  stages{
      stage("Cleanup Workspace"){
            steps {
              cleanWs()
              }
      }
      stage("Checkout from SCM"){
            steps {
                git branch: 'main', credentialsId: 'github', url: 'https://github.com/satish1137/register-app-jenkins_project.git'

            }
      }
      stage("Build Application"){
            steps {
                sh "mvn clean package"
            }
      }
      stage("Test Application"){
            steps {
                sh "mvn test"
            }
      }
  }

}
