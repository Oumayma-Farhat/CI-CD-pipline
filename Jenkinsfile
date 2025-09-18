pipeline {
    agent any

    stages {


        stage('checkout') {
            steps {
                git url: 'https://github.com/Oumayma-Farhat/CI-CD-pipline.git', branch: 'main'
                sh "ls -ltr"
                }
            
            }
            
        stage('setup') {
            steps{
                sh "pip install -r requirements.txt"
            } 
        }   

        }
        stage('Test') {
            steps {
                sh "pytest"
                
            }
        }
    }
