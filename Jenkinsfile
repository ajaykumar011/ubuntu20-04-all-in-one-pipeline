pipeline {
    agent none 
    stages {
        stage('Version Check') {
            agent { docker 'ajaykumar011/ubuntu20-04-all-in-one' } 
            steps {
                echo 'Hello, All-in-One'
                sh 'nginx -V'
            }
        }
        stage('Example Test') {
            agent { docker 'openjdk:8-jre' } 
            steps {
                echo 'Hello, JDK'
                sh 'java -version'
            }
        }
    }
}
