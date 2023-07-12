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
            stage('unit test Maven'){

            steps {
              script{
                
                  mvnTest()
              }
                }
            }
        }
        // Add more stages as needed
    }

