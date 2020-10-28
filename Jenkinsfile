pipeline {
    agent none 
    stages {
        stage('Version Check') {
            agent { 
                docker {
                    image 'ajaykumar011/ubuntu20-04-all-in-one' 
                    args '-v app:/app -p 81:80 -p 2222:22'
                    }
                }
            steps {
                echo 'Hello, All-in-One'
                sh 'nginx -V'
                sh 'curl localhost:80'
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
