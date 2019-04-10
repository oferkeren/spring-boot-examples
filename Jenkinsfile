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
                sh 'mvn -B -f $WORKSPACE/spring-boot-package-war/pom.xml -DskipTests clean package'
            }
        }
       
    }
  
}
