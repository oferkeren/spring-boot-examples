pipeline {
    agent any
    tools {
        maven "Maven"
    }
    stages {
        stage('checkout') {
            steps {
                deleteDir()
                checkout scm
            }
        } 
        stage('Build') {
            steps {
                sh 'mvn -f $WORKSPACE/spring-boot-package-war/pom.xml'
            }
        }
       
    }
  post {
     always {
         junit 'target/surefire-reports/*.xml'
         }
    }
}
