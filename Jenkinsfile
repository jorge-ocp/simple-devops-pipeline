pipeline {
    agent any
    stages {
        stage('Terraform init') {
            steps {
                sh 'cd terraform && terraform init --upgrade'
                sh 'terraform -v'
            }
        }
        stage('Terraform plan') {
            steps {
                withAWS(credentials: 'devops-credentials-2'){
                    sh 'cd terraform && terraform plan'

                }
                
            }
        }  
    }
}
