pipeline{
    agent any
    stages{
        stage('SCM Checkout'){
            steps{
             git branch: 'dev', credentialsId: '5243e135-536c-499f-9a11-b08bf8cdfe8f', url: 'https://github.com/deepashre/multi-dev-prod-apache.git'
            }
           
        }
        stage('Execute Ansible'){
            steps{
                ansiblePlaybook credentialsId: 'private-key', disableHostKeyChecking: true, installation: 'ansible2', inventory: 'dev.inv', playbook: 'apache.yml'
            }
        }
    }
    
}
