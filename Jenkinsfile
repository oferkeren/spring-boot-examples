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
                sh 'mvn -f $WORKSPACE/spring-boot-package-war/pom.xml clean install'
            }
        }
        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }
       
    }
  post {
     always {
         junit 'target/surefire-reports/*.xml'
         }
    }
}
