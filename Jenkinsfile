pipeline {
    agent {
        label 'nodejs_slave1'
    }

    tools {
        nodejs "Node"
    }

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'Development',
                    url: 'https://github.com/Anurag-Evervent/express_server_for_flutter_app_testing.git'
            }
        }
        
        stage('Install Dependencies') {
            steps {
                sh 'npm install'        
            }
        }
        
        stage('Install pm2') {
            steps {
                sh 'npm install pm2 -g'
            }
        }
        
        stage('Deploy') {
            steps {
                sh 'pm2 startOrRestart pm2.config.json'
            }
        }
    }
}
