pipeline {
    agent any 
    environment {
        // ADD Maven path environment
        PATH = "/miniconda3/bin:$PATH"
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
                conda init bash
                echo "[INFO] Updating conda"
                conda update -q conda
                echo '[INFO] Successfully updated miniconda :)'
                
                echo "[INFO] Creating ${myEnv}..."
                conda create -y -n my-env python=3.9
                echo "[INFO] Successfully created ${myEnv}"
                conda activate ${myEnv}
                echo "[INFO] ${myEnv} has been successfully activated"
                echo "[INFO] Successfully installed miniconda"
                """
            }
        }
        stage("Install Django"){
            steps {
                sh """
                pip install django -y
                echo "[INFO] Django was successfully installed
                """
            }
        }
    }
}