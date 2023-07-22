pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Checkout the source code from your version control system (e.g., Git)
                git 'https://github.com/your/repo.git'
                // Install Python dependencies
                bat 'pip install -r requirements.txt'
            }
        }


        stage('Package') {
            steps {
                // Create the Docker image for your Python application
                sh 'docker build -t python-proj-img .'
            }
        }

        stage('Deploy') {
            steps {


                // Use a tool like SSH to remotely execute commands on the server (assumes you've set up SSH keys for passwordless access)

                    bat 'docker run -d --name python-proj -p 8080:8080 python-proj-img'

            }
        }
    }
}