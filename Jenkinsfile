pipeline {
  agent {label 'core'}
    stages {
        stage('vcs') {
            steps {
                git branch: 'main', url: 'https://github.com/nagarjuna33/saleor.git'
            }
        }
        stage('docker image build') {
            steps {
                sh 'docker image build -t saleorcore:dev .'
                sh 'docker image tag saleorcore:dev nagarjunaduggireddy/ saleorcore:DEV'
            }
        }
        stage('push image to registry') {
            steps {
                sh 'docker image push nagarjunaduggireddy/ saleorcore:DEV'
            }
        }
    }
}
