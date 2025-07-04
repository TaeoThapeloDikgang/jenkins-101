pipeline {
    agent { 
        node {
            label 'docker-agent-python'
            }
      }
    triggers {
        pollSCM '* * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh 'cd myapp'
                sh 'PIP_BREAK_SYSTEM_PACKAGES=1 pip install -r requirements.txt'
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                    cd myapp
                    python3 hello.py
                    python3 hello.py --name=Brad
                '''
                
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}
