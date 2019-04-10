pipeline {
    agent any
    tools {
        maven "Maven"
    }
    stages {
        stage('Checkout Code') {
            steps {
                deleteDir()
                checkout scm
            }
        } 
        stage('Build Version ${BUILD_NUMBER}') {
            steps {
                sh 'mvn -B -f $WORKSPACE/spring-boot-package-war/pom.xml clean package'
            }
        }
       
    }
  
}
