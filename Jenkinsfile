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
                // Build the package
                sh 'apt dpkg-buildpackage -us -uc'
            }
        }
    }
}
