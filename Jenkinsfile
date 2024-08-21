pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                // Checkout the source code from your repository
                checkout scm
            }
        }
        stage('Build') {
            steps {
                // Install necessary packages
                //sh 'yum update'
                sh 'sudo apt install -y build-essential devscripts debhelper'
                // Build the package
                sh 'dpkg-buildpackage -us -uc'
            }
        }

    }
}
