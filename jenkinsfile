pipeline {
  agent { label 'jenkins-Agent' }
  tools { 
      jdk 'java17'
      maven 'maven3'
      }
  stages{
      stage("Cleanup Workspace"){
            steps {
              cleanWs()
              }
      }
      stage("Checkout from SCM"){
            steps {
                git branch: 'main', credentialsId: 'github', 'https://github.com/satish1137/register-app-jenkins_project.git'
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
