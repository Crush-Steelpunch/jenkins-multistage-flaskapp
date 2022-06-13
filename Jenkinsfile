pipeline {
    agent any
    stages {
        stage('GetCode') {
            steps {
                git changelog: false, poll: false, url: 'https://github.com/Crush-Steelpunch/hangman.git'
            }
        }
        stage('Test') {
            steps {
                sh '''#!/bin/bash
                    python3 -m venv venv
                    source venv/bin/activate
                    pip3 install -r requirements.txt'''
            }
        }
        stage('Deploy') {
            steps {
                sh '''#!/bin/bash
                    sudo systemctl restart hangman'''
            }
        }
    }
}