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
                sh "sed -i '11s/Hello World xx/Hello World/' $WORKSPACE//spring-boot-package-war/src/main/java/com/neo/controller/HelloWorldController.java"
                sh 'mvn -B -f $WORKSPACE/spring-boot-package-war/pom.xml clean package'
            }
        }
       
    }
  
}
