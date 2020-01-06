pipeline {
    agent any
    stages {
        stage('Buildm') {
            //parallel {
            //    stage('Compile1') {
                    steps {
                        sleep(20)
                        snDevOpsStep()
                        //sh 'mvn clean package -DskipTests=true'
                        //sh 'mvn surefire:test'
                        //junit 'target/surefire-reports/TEST-*.xml'
                    }
              //  }
                //stage('Compile2') {
                  //  steps {
                    //    snDevOpsStep (stepSysId:'2decb637c73333008c2c02b827c2609c')
                        //sh 'mvn clean package -DskipTests=true'
                    //}
                //}
            //}
        }
        stage('Testm') {
            steps {
                sleep(20)
                snDevOpsStep()
                //sh 'mvn surefire:test'
            }
        }
        stage('Deploym') {
            steps {
                sleep(10)
                snDevOpsStep()
               sh 'mvn clean package -DskipTests=true'
               sh 'mvn surefire:test'
               junit 'target/surefire-reports/TEST-*.xml'
               sleep(25)
            }
        }
        stage('Prodm') {
            //snDevOpsStep "ec633729c7b333008c2c02b827c26019"
            //parallel {
              //  stage("Publish Junit") {
                    //steps {
                      //  snDevOpsStep (stepSysId:'29ecb637c73333008c2c02b827c2609c')
                        //snDevOpsChange()
                        //junit 'target/surefire-reports/TEST-*.xml'
                    //}
                //}
                //stage("Publish Cucumber") {
                    steps {
                        sleep(11)
                        snDevOpsStep()
                        snDevOpsChange()
                        //junit 'target/surefire-reports/TEST-*.xml'
                        //cucumber "**/cucumber.json"
                        //echo "test"
                  //  }
                //}
            }
        }
    }
}
