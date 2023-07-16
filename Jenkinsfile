pipeline {
    agent any
    environment {
        PATH = "$PATH:/usr/share/maven/bin"
    }
    stages {
        stage('GetCode') {
            steps {
                git 'https://github.com/anildevops7702/new-jenkins-maven.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage('SonarQube analysis') {
            steps {
                sh 'mvn clean verify sonar:sonar \
                    -Dsonar.projectKey=anil1\
                    -Dsonar.host.url=http://18.237.181.248:9000 \
                    -Dsonar.login= 29c99806119e69d9cb2d958e0076257e6ae8497e'
            }
        }
    }
}
