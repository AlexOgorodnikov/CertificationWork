pipeline {
    agent any
   
    stages {
        stage("provisionind dev and app servers") {
             environment {
                AWS_ACCESS_KEY_ID = credentials('AWS_ACCESS_KEY_ID')
                AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
            }
             steps {
                script {
                        sh "terraform init"
                        sh "terraform apply --auto-approve"
                    }
                }

           }
            
        stage("building and deploying app with ansible playbook") {
            environment {
                AWS_ACCESS_KEY_ID = credentials('AWS_ACCESS_KEY_ID')
                AWS_SECRET_ACCESS_KEY = credentials('AWS_SECRET_ACCESS_KEY')
                sshCredsID = 'ssh _key'
            }
            steps {
                
                ansiblePlaybook(
                    playbook: 'build_and_deploy_app.yml',
                    inventory: 'inv_aws_ec2.yml',
                    credentialsId: "${sshCredsID}",
                    disableHostKeyChecking: true,
                    become: true,
                )
            }
        }
    } 
}
