pipeline {
    agent none
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
        stage('refactory') {
            agent any
            steps {
                sh 'pwd'
                sh 'cp ./target/my-app-1.0-SNAPSHOT.jar /var/jenkins_home/haohan/DDoSWeb/jar'
            }
        }
    }
}