pipeline {
    agent any
    stages {
        stage(Compile) {
            parallel {
                stage('Compile1') {
                    steps {
                        snDevOpsStep "e0633729c7b333008c2c02b827c2601a"
                        sh 'mvn clean package -DskipTests=true'
                        sh 'mvn surefire:test'
                        junit 'target/surefire-reports/TEST-*.xml'
                    }
                }
                stage('Compile2') {
                    steps {
                        snDevOpsStep "e0633729c7b333008c2c02b827c2601a"
                        //sh 'mvn clean package -DskipTests=true'
                    }
                }
            }
        }
        stage('Unit Tests') {
            steps {
                snDevOpsStep "60633729c7b333008c2c02b827c2601a"
                //sh 'mvn surefire:test'
            }
        }
        stage('Integration Tests') {
            steps {
                snDevOpsStep "e4633729c7b333008c2c02b827c26019"
                sh 'mvn failsafe:integration-test'
                junit 'target/surefire-reports/TEST-*.xml'
            }
        }
        stage('Publishing Tests') {
            //snDevOpsStep "ec633729c7b333008c2c02b827c26019"
            parallel {
                stage("Publish Junit") {
                    steps {
                        snDevOpsStep 'ec633729c7b333008c2c02b827c26019'
                        //snDevOpsChange()
                        //junit 'target/surefire-reports/TEST-*.xml'
                    }
                }
                stage("Publish Cucumber") {
                    steps {
                        snDevOpsStep 'ec633729c7b333008c2c02b827c26019'
                        cucumber "**/cucumber.json"
                    }
                }
            }
        }
    }
}
