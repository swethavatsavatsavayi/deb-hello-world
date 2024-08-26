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
                sh 'dpkg-buildpackage -b -us -uc'
            }
        }
        stage('Archive Aritfact') {
            steps {
                //Store artifact
                sh '''
                    pwd
                    cd ..
                    pwd
                '''
                archiveArtifacts artifacts: '*.deb'
            }
        }

    }
}
