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
                
            dir('maventdd') {
             sh "'${m3}/bin/mvn' clean compile"
            }
         
         }
        
    }


        






        
    

    }
}