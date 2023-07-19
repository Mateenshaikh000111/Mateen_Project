@Library('my-shared-library') _

pipeline {
    agent any

    parameters {
        choice(name: 'action', choices: 'Create\nDelete', description: 'choose Create/Destroy')
    }

    stages {
        stage('Git Checkout') {
            when {
                expression { params.action == 'Create' }
            }
            steps {
                gitCheckout(
                    branch: "main",
                    url: "https://github.com/Mateenshaikh000111/Mateen_Project.git"
                )
            }
        }

        stage('Unit Test Maven') {
            when {
                expression { params.action == 'Create' }
            }
            steps {
                script {
                    mvnTest()
                }
            }
        }

        stage('Integration Test Maven') {
            when {
                expression { params.action == 'Create' }
            }
            steps {
                script {
                    mvnintegrationTest()
                }
            }
        }

        stage('Static Code Analysis Sonarqube') {
            when {
                expression { params.action == 'Create' }
            }
            steps {
                script {
                    def SonarQubecredentialsId = 'SonarQube_API'
                    StaticCodeAnalysis(SonarQubecredentialsId)
                }
            }
        }
        stage('Quality gate status') {
            when {
                expression { params.action == 'Create' }
            }
            steps {
                script {
                    def SonarQubecredentialsId = 'SonarQube_API'
                    QualityGateStatus(SonarQubecredentialsId)
                }
            }
        }
         stage('Maven Build : maven') {
            when {
                expression { params.action == 'Create' }
            }
            steps {
                script {
                    
                    mvnBuild()
                }
            }
        }
    }
}
