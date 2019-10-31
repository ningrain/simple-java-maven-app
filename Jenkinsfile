pipeline {
    agent any
    stages {
        stage('Build') {
            agent {
                docker {
                    image 'maven:3-alpine'
                    args '-v /root/.m2:/root/.m2'
                }
            }
            steps {
                sh 'mvn -B -DskipTests clean package' 
            }
        }
        stage('Deliver') {
            steps {
                sh 'cp /usr/local/jenkins-data/workspace/simple-java-maven-app/target/my-app-1.0-SNAPSHOT.jar /root'
            }
        }
    }

}