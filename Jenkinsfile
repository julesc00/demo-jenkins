pipeline {
    agent any 
    environment {
        // ADD Maven path environment
        myEnv = "my-env2"
    }
    stages {
        stage("Git Checkout") {
            steps {
                git branch: 'main', url: 'https://github.com/julesc00/demo-jenkins.git'
            }
        }
        stage("Maven Build") {
            steps {
                
                echo "Someday this will work"
            }
        }
        stage("Install Python 3 and Django") {

            steps {
                // Update Python to version 3
                sh """
                mkdir -p /home/ec2-user/app && cd /home/ec2-user/app
                pip install --user pipenv
                pipenv shell
                pipenv install django
                """
            }
        }
    }
}