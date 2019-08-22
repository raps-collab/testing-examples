pipeline {
    agent any
    stages {
        stage('Compile') {
            steps {
                snDevOpsStep "3de392a3c7d333008c2c02b827c26099"
                sh 'mvn clean package -DskipTests=true'
            }
        }
        stage('Unit Tests') {
            steps {
                snDevOpsStep "b9e392a3c7d333008c2c02b827c26099"
                sh 'mvn surefire:test'
            }
        }
         stage('Integration Tests') {
            steps {
                snDevOpsStep "31e392a3c7d333008c2c02b827c26099"
                sh 'mvn failsafe:integration-test'
            }
        }
        stage('Publishing Tests') {
            steps {
                snDevOpsStep "39e392a3c7d333008c2c02b827c26099"
                junit 'target/surefire-reports/TEST-*.xml'
            }
        }
    }
    
}
