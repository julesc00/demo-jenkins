pipeline {
    agent any 
    environment {
        // ADD Maven path environment
        PATH = "WORKSPACE/miniconda/bin:$PATH"
        myEnv = "my-env"
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
                echo "[INFO] Start downloading miniconda"
                sh """
                wget https://repo.anaconda.com/miniconda/Miniconda3-py39_4.12.0-Linux-x86_64.sh -O miniconda.sh
                echo '[INFO] Successfully downloaded miniconda'

                hash -r
                conda init bash
                conda config --set always_yes yes --set changeps1 no
                echo "[INFO] Updating conda"
                conda update -q conda
                echo '[INFO] Successfully installed and updated miniconda :)'
                
                echo "[INFO] Creating ${myEnv}..."
                conda create -y -n my-env python=3.9
                echo "[INFO] Successfully created ${myEnv}"
                conda activate ${myEnv}
                echo "[INFO] ${myEnv} has been successfully activated"
                echo "[INFO] Successfully installed miniconda"
                """
            }
        }
        stage("Test conda") {
            steps {
                sh '''#!/usr/bin/env bash
                source $WORKSPACE/miniconda/etc/profile.d/conda.sh
                echo "[INFO] Conda was tested successfully!"
                '''

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