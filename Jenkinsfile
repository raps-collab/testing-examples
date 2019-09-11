pipeline {
  agent any
  tools {
    maven "maven"
 }
  stages {
      stage("build") {
          steps {
              echo "Building...."
              snDevOpsStep '0963f7b1c77333006234c4047e9763c8'
              sh 'mvn test -Dpublish'
               junit '**/target/surefire-reports/*.xml'
              sleep 10
          }
      }
      stage("test") {
           steps {
                  echo "Testing.."
                  snDevOpsStep '8163f7b1c77333006234c4047e9763c9'
             //snDevOpsChange()
        sleep 10
           }
       }
      stage("deploy") {
          steps {
              echo "Deploying..."

              snDevOpsStep '0163f7b1c77333006234c4047e9763c9'
              //snDevOpsChange()

              sleep 10
          }
      }
  }
}
