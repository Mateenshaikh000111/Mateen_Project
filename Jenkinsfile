@Library('my-shared-library')

pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                script {
                    gitCheckout(
                        branch: 'main',
                        url: 'https://github.com/Mateenshaikh000111/Mateen_Project.git'
                    )
                }
            }
        }
        // Add more stages as needed
    }
}
