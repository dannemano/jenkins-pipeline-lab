pipeline {
    agent any
    tools {
        maven 'maven_3.5.0'
        jdk 'JDK8'
    }
    options {
        buildDiscarder(logRotator(numToKeepStr: '4'))
    }
    stages {
        stage ('Initialize') {
            steps {
                sh '''
                    echo "PATH = ${PATH}"
                    echo "M2_HOME = ${M2_HOME}"
                '''
            }
        }

        stage ('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
    }
}