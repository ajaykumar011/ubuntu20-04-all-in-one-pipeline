pipeline {
    agent none 
    stages {
        stage('Php Lint') {
            agent { 
                docker {
                    image 'ajaykumar011/ubuntu20-04-all-in-one' 
                    args '-v app:/app -p 81:80 -p 2222:22'
                    }
                }
            steps {
                echo 'Hello, Lint check'
                sh 'nginx -v'
                sh 'find app/ -name "*.php" -print0 | xargs -0 -n1 php -l'

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
