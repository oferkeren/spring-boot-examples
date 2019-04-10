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
        stage('Build the code') {
            steps {
                sh "sed -i '11s/Hello World xx/Hello World/' $WORKSPACE//spring-boot-package-war/src/main/java/com/neo/controller/HelloWorldController.java"
                sh 'mvn -B -f $WORKSPACE/spring-boot-package-war/pom.xml -DskipTests clean package'
            }
        }
        stage('Unit Tests') {
            steps {
                sh 'mvn test -f $WORKSPACE/spring-boot-package-war/pom.xml'
            }
        }
       
    }
    post {
     always {
         junit 'spring-boot-package-war/target/surefire-reports/*.xml'
         }
    }
  
}
