pipeline {
    agent any
    stages {
        stage('CI') {
            steps {
                snDevOpsStep()
                
            }
        }
        stage('UAT deploy') {
            stages {
                stage("Staging-Deploy") {
                    steps {
                        snDevOpsStep()
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
                                //sh "mvn javadoc:jar"
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
                        snDevOpsStep()
                        //snDevOpsChange()
                        //sh '''
                          //  export M2_HOME=/opt/apache-maven-3.6.0 # your Mavan home path
                            //export PATH=$PATH:$M2_HOME/bin
                            //mvn --version
                        //'''
                    }
                    post {
                        success {
                            //junit '**/target/surefire-reports/*.xml' 
                            echo 'test'
                        }
                    }
                }
                stage('UAT static code test') {
                    steps {
                         snDevOpsStep()
                        // snDevOpsChange()
                       
                    }
                }
            }
        }
        
        stage('Pre Prod') {
           stages {
            stage('Pre_Prod_Sub1') {
                steps {
                    //sh 'mvn --version'
                    echo 'test'
                }
             }
             stage('Pre_Prod_Sub2') {
                steps{
                    //sh 'mvn --version'
                    echo 'test'
                }
             }
            }
        }
         
        stage('PROD') {
           stages{
             stage('sub-prod') {
               steps {
                    //sh 'mvn --version '
                    snDevOpsStep()
                    snDevOpsChange()
                }
             }
           }
        }
    }
}
