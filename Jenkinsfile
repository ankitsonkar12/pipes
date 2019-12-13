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
                checkout scm
            }
        }


        stage('Complile'){
            steps{
                mvn clean compile
                
            
         
         }
        
    }


        






        
    

    }
}
