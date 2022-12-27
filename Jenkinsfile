pipeline{
    agent any
    tools{
       maven "3.6.3"
    }
    stages{
       stage('source'){
          steps{
          git branch: 'main', url: 'https://github.com/bayeserigneseck40/projet-sir-2022.git'
          }
       }
         stage('build'){
                 steps{
                   bat 'mvn clean org.jacoco:jacoco-maven-plugin:prepare-agent install'
              }
    }
     stage('SonarQube Analysis'){
                steps{
                     bat 'mvn sonar:sonar'
                  }
}
      stage('Approve Deployement'){
                   input{
                      message 'Do you want to proced for Deployement'
                      }
                      steps{
                          bat 'echo Deploying into server'
                      }

                   }
      }
      post{
        aborted{
           echo 'Sending message to Agent'
        }
        failure{
             echo 'Sending Message to Agent'
        }
      }

      }
