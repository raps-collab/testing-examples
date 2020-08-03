pipeline {
    agent any
    stages {
        
        stage('CI-Test') {
            steps {
                sleep 10              
            }
        }
        
        stage('CI') {
            steps {
                echo 'test'
            }
        }
        stage('UAT deploy') {
            stages {
                stage("Staging-Deploy") {
                    steps {
                        echo 'test'
                    }
                }
                stage("Send-Report") {
                    stages {
                        stage("Alert-If-Issues") {
                            steps {
                                echo 'test'
                            }
                        }
                        stage("Conclude") {
                            steps {
                                echo 'test'
                            }
                        }
                    }
                }
            }
        }
        stage('UAT test') {
            parallel {
                stage('UAT test test1') {
                    steps {
                         echo 'test'
                    }
                    post {
                        success {
                            echo 'test'
                        }
                    }
                }
                stage('UAT static code test') {
                    steps {
                            echo 'test'
                    }
                }
            }
        }
        
        stage('Pre Prod') {
           stages {
            stage('Pre_Prod_Sub1') {
                steps {
                    echo 'test'
                }
             }
             stage('Pre_Prod_Sub2') {
                steps{
                    echo 'test'
                }
             }
            }
        }
         
        stage('PROD') {
           stages{
             stage('sub-prod') {
               steps {
                    snDevOpsChange()
                }
             }
           }
        }
    }
}
