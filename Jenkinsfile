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
    }
}