pipeline {
    agent any
    environment {
        SSH_CRED = credentials('SSH_CRED')
    }
    stages {
        stage ('Lint Checks') {
            steps{
                sh "env"
                sh "echo runs only on feature branch"
                sh "echo lint checks are completed"
            }
        }
        stage ('Performing a dry run') {
            steps {
                sh "env"
                sh "echo Runs only against a PR"
                //sh "ansible-playbook robot-dryrun.yml  -e COMPONENT=mongodb -e ansible_user=${SSH_CRED_USR} -e ansible_password=${SSH_CRED_PSW} -e ENV=dev"
            }
        }
        stage ('Three') {
            steps {
                sh "env"
                sh "echo Main Branch"
            }
        }
        stage('Runs against Tag') {
            when { expression { env.TAG_NAME != null } }                       // TAG_NAME is an environment
            steps {
                sh "env"
                sh "echo $TAG_NAME"
            }
        }
    }
}
//pushing changes to feature branch