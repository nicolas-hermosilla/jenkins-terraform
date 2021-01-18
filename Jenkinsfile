properties([pipelineTriggers([githubPush()])])

environment {
        AWS_ACCESS_KEY_ID     = credentials('AKIAXEQG34BCIXW5DLMM')
        AWS_SECRET_ACCESS_KEY = credentials('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')
        AWS_REGION      = 'eu-west-3'
   } 

pipeline {
    agent {

        environment {
          AWS_ACCESS_KEY_ID     = credentials('AKIAXEQG34BCIXW5DLMM')
          AWS_SECRET_ACCESS_KEY = credentials('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')
          AWS_REGION      = 'eu-west-3'
        }
        docker {
            image 'hashicorp/terraform'
            args '--entrypoint='
        }
    }
    stages {
        stage('Init Terraform directory') {
            steps {
                sh 'terraform init'
            }
        }
        stage('Plan terraform code') {
            steps {
                sh 'terraform plan'
            }
        }
        stage('Apply terraform code') {
            steps {
                sh 'terraform apply -auto-approve'
            }
        }
    }
}
