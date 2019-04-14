pipeline {
    agent any
    parameters {
        choice(name: 'AMI_NAME', choices: ['ubuntu-with-java'], description: 'Pick an AMI config')
    }
    stages {
        stage('Bake AMI') {
            environment {
                AWS_ACCESS_KEY = credentials('aws-access-credential')
            }
            steps {
                sh 'packer build ${AMI_NAME}-config.json'
            }
        }
    }
}