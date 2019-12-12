pipeline{
    agent any
    tools{
        maven "m3"
    }
    triggers{
        pollSCM("* * * * *")
    }
    stages{
        stage('Checkout'){
        git url:"https://github.com/atinsingh/w18.git", branch: "${BRANCHNAME}"
        sh 'echo "${BRANCHNAME}"'
    }
    stage('Complile'){
         def mvnHome = tool 'm3'
         dir('maventdd') {
             sh "'${mvnHome}/bin/mvn' clean compile"
         }
        
    }
    stage('Testing'){
         def mvnHome = tool 'm3'
          dir('maventdd') {
             sh "'${mvnHome}/bin/mvn' test"
         }
    }
    stage('Integration Test'){
         def mvnHome = tool 'm3'
           dir('maventdd') {
             sh "'${mvnHome}/bin/mvn' package"
         }
    }
    if("${BRANCHNAME}"=="master"){
        stage('Deploymennt'){
                dir('maventdd') {
                sh "'${mvnHome}/bin/mvn' install"
            }
        }
    }else {
        stage('No Deployment'){
            sh "echo ${BRANCHNAME}"
        }

        
    }
}