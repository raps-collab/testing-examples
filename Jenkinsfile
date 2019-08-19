pipeline {
    agent any
    stages {
        stage('Compile') {
            steps {
                snDevOpsStep "80478221c7d33300b8e302b827c260b5"
                sh 'mvn clean package -DskipTests=true'
            }
        }
        stage('Unit Tests') {
            steps {
                snDevOpsStep "00478221c7d33300b8e302b827c260b5"
                sh 'mvn surefire:test'
            }
        }
         stage('Integration Tests') {
            steps {
                snDevOpsStep "08478221c7d33300b8e302b827c260b4"
                sh 'mvn failsafe:integration-test'
            }
        }
        stage('Publishing Tests') {
            steps {
                snDevOpsStep "8c478221c7d33300b8e302b827c260b4"
                junit 'target/surefire-reports/TEST-*.xml'
            }
        }
    }
    
}
