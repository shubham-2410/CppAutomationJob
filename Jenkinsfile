pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                checkout scm
                echo "Repository Cloned"
            }
        }
        stage('Build') {
            steps {
                bat '''
                echo "Current directory:"
                cd
                echo "Files in directory:"
                dir
                set PATH=C:\\MinGW\\bin;%PATH%
                g++ -o main.exe main.cpp
                '''
                echo "Build Completed"
            }
        }
        stage('Run Program') {
            steps {
                bat '''
                if exist main.exe (
                    .\\main.exe
                ) else (
                    echo "Build failed. main.exe not found!"
                    exit /b 1
                )
                '''
                echo "Program ran successfully"
            }
        }
    }
}
