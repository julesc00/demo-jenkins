pipeline {
    agent any 
    stages {
        state("Git Checkout") {
            steps {
                git branch: 'main', url: 'https://github.com/julesc00/demo-jenkins.git'
            }
        }
    }
}