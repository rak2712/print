pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/rak2712/print.git'  // Change this!
            }
        }
        
        stage('Install Python') {
            steps {
                sh '''
                if ! command -v python3 &> /dev/null
                then
                    sudo apt update
                    sudo apt install -y python3 python3-pip
                else
                    echo "Python3 already installed"
                fi
                '''
            }
        }
        
        stage('Run Python script') {
            steps {
                sh 'python3 print_name.py'
            }
        }
    }
}
