pipeline {
  agent any
  tools {
    maven "maven"
 }
  stages {
      stage("build") {
          steps {
              echo "Building...."
              snDevOpsStep 'e0633729c7b333008c2c02b827c2601a'
              sh 'mvn test -Dpublish'
               junit '**/target/surefire-reports/*.xml'
              sleep 10
          }
      }
      stage("test") {
           steps {
                  echo "Testing.."
                  snDevOpsStep '60633729c7b333008c2c02b827c2601a'
             //snDevOpsChange()
        sleep 10
           }
       }
      stage("deploy") {
          steps {
              echo "Deploying..."

              snDevOpsStep 'e4633729c7b333008c2c02b827c26019'
              //snDevOpsChange()

              sleep 10
          }
      }
  }
}
