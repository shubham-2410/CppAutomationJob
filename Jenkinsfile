pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                bat '"C:\\MinGW\\bin\\g++.exe" -o program main.cpp'
                echo "Build Completed"
            }
        }
        stage('Run Program') {
            steps {
                bat 'program.exe'
                echo "Program runned Successsfully"
            }
        }
    }
}
