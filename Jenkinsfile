pipeline {
    agent any

    stages {
        stage('preparation') {
            steps {
                git 'https://github.com/mohamedkaoud14/Booster_CI_CD_Project'
            }
        }
        stage('CI') {
            steps {
                sh 'docker build . -t kaoud/django_cicd:1.0'
            }
        }
        stage('CD') {
            steps {
                sh 'docker run -d -p 8000:8000 kaoud/django_cicd:1.0'
            }
            
            post{
            	success{
            		slackSend (color:"#52a832", message: "completed successfully")
            	}
            }
        }
        
    }
}

