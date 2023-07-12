@Library('my-shared-library') _

pipeline{

    agent any

    stages{

        stage('Git Checkout'){

            steps {
            gitCheckout(
                    branch: "main",
                    url: "https://github.com/Mateenshaikh000111/Mateen_Project.git"
                    )
                }
            }
        }
        // Add more stages as needed
    }

