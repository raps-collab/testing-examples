pipeline {
    agent any
    stages {
        stage(Compile1) {
            //parallel {
            //    stage('Compile1') {
                    steps {
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
        stage('Unit Tests1') {
            steps {
                snDevOpsStep()
                //sh 'mvn surefire:test'
            }
        }
        stage('Integration Tests2') {
            steps {
                snDevOpsStep()
               sh 'mvn clean package -DskipTests=true'
               sh 'mvn surefire:test'
               junit 'target/surefire-reports/TEST-*.xml'
               sleep(10)
            }
        }
        stage('Publishing Tests1') {
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
                        snDevOpsStep()
                        sleep(60);
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
