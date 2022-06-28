pipeline {
    agent any 
    environment {
        // ADD Maven path environment
        PATH = "/opt/maven-3.8.6/bin:$PATH"
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
                wget https://repo.anaconda.com/miniconda/Miniconda3-py39_4.12.0-Linux-x86_64.sh &&
                sudo chmod +x Miniconda3-py39_4.12.0-Linux-x86_64.sh &&
                ./Miniconda3-py39_4.12.0-Linux-x86_64.sh
                """
                // Install Conda
                "conda create -n my-env python=3.9 -y && conda activate my-env"
                "pip install django"
            }
        }
    }
}