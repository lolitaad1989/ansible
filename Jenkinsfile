pipeline {
    agent any
    environment {
        SSH_CRED = credentials('SSH_CRED')
    }
    stages {
        stage('Lint Checks') {
            when { branch pattern: "feature*", comparator: "REGEXP" }
            steps {
                sh "env"
                sh "echo runs only on feature branch"
                sh "echo lint cheks are completed."
            }
        }  

        stage('Performing a Dry-Run') {                 // Just for demo purpose we have hardcoded env and component; That can still be parameterised.
            when { branch pattern: "PR-.*", comparator: "REGEXP"}
            steps {
                sh "env"
                sh "Runs only aginst a PR"
            }
        }

        stage('Runs against Main') {
            when { branch 'main' }
            steps {
                sh "env"
                sh "echo Main Branch"
            }
    }
}
}
//pushing changes to feature branch