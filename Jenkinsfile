pipeline {
    agent any
    }
    stages {
        stage('Build') {
            steps {
                echo 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                echo 'mvn test'
            }
            post {
                always {
                    echo 'junit used to generate target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') {
            steps {
                echo 'Run bash script ./jenkins/scripts/deliver.sh'
            }
        }
    }
}
