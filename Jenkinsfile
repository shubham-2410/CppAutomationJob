pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/shubham-2410/CppAutomationJob.git'
                echo "Repository Cloned"
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
