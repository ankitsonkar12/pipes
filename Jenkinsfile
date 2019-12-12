pipeline{
    agent any
    tools{
        maven "m3"
    }
    triggers{
        pollSCM("* * * * *")
    }
    stages{
        stage('checkout')
        {
            steps{
                git ' https://github.com/ankitsonkar12/pipes.git' 
            }
        }


        stage('Complile'){
            steps{
                def mvnHome = tool 'm3'
         dir('maventdd') {
             sh "'${mvnHome}/bin/mvn' clean compile"
            }
         
         }
        
    }


        






        
    

    }
}