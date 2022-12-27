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
                   bat 'mvn clean package'
              }
    }
   
      }
}
