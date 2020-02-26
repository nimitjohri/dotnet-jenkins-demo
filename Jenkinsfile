pipeline {
agent any

environment {
   PATH = "C:\\Windows\\System32"
}

stages {
stage ('Checkout') {
        steps{
            git 'https://github.com/nimitjohri/dotnet-jenkins-demo.git' 

        }
    }
stage ('Restore Packages') {     
         steps {
             bat '"C:\\Program Files\\dotnet\\dotnet.exe" restore "dotnet-jenkins-demo\\jenkins-demo.sln" ' 
          }
        }
// stage('Clean') {
//       steps {
//             bat '"C:\\Program Files\\dotnet\\dotnet.exe" clean'
//        }
//     }
stage('Build') {
     steps {
            bat "\"${tool 'MSBuild'}\" dotnet-jenkins-demo\\jenkins-demo.sln /p:Configuration=Debug /p:Platform=\"Any CPU\" /p:ProductVersion=1.0.0.${env.BUILD_NUMBER}"
      }
   }
 }
}