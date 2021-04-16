pipeline {
    agent any
    environment{
        myvar="outer block"
    }
    
    stages {
        stage('checkout'){
            steps{
            git branch: 'main', credentialsId: 'gopigithubid', url: 'https://github.com/saigopinath8466/bash-scripts.git'
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
