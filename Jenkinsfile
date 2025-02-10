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
                g++ -o program main.cpp 2> errors.log
                if %ERRORLEVEL% NEQ 0 (
                    echo "Compilation failed. Check errors.log"
                    exit 1
                )
                '''
                echo "Build Completed"
            }
        }
        stage('Run Program') {
            steps {
                bat '''
                if exist program.exe (
                    program.exe
                ) else (
                    echo "Build failed. program.exe not found!"
                    exit 1
                )
                '''
                echo "Program ran successfully"
            }
        }
    }
}
