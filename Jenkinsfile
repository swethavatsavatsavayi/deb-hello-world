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
                sh 'apt update'
                sh 'apt install -y build-essential devscripts debhelper'

                // Build the package
                sh 'dpkg-buildpackage -us -uc'
            }
        }

        stage('Archive Artifacts') {
            steps {
                // Archive the Debian package
                archiveArtifacts artifacts: '*.deb', allowEmptyArchive: true
            }
        }
    }
}
