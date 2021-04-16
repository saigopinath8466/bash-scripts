pipeline {
    agent any
    environment{
        myvar="outer block"
    }
    
    stages {
        stage('checkout'){
            steps{
            checkout scm
            }
        }
        stage('build'){
            steps{
            sh "sh array.sh"
            }
        }
        stage('post task'){
            steps{
            sh "echo emailing"
            }
        }
        stage('environment variables'){
            environment {
                myvar="inner block"
            }
            steps{
            sh 'echo "this is my variable: $myvar"'
            }
        }
    }
}
