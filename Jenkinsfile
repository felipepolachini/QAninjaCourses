pipeline{
    agent any
    
    stages{
            stage('Build'){
                    steps{
                        echo "Building and solving dependencies"
                        sh "bundle install"
                    }    
            }
            stage('Test'){
                    steps{
                        echo "Running regression tests"
                    }    
            }
            stage('UAT'){
                    steps{
                        echo "Wait for User Acceptance"
                        input(message: 'Go to production?' , ok:'Yes')
                    }
            }
            stage('Prod'){
                    step{
                        echo "WebApp is ready."
                    }
            }
    }
}
