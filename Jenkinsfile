pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                script {
                    // Pull the Docker image
                    bat 'docker pull python:3-alpine'
                    // Run commands inside the Docker container
                    bat '''
                    docker run --rm ^
                    -v "%WORKSPACE%":/workspace ^
                    -w /workspace ^
                    python:3-alpine ^
                    sh -c "python -m py_compile sources/add2vals.py sources/calc.py"
                    '''
                }
            }
        }
        stage('Test') {
            steps {
                script {
                    // Pull the Docker image
                    bat 'docker pull qnib/pytest'
                    // Run tests inside the Docker container
                    bat '''
                    docker run --rm ^
                    -v "%WORKSPACE%":/workspace ^
                    -w /workspace ^
                    qnib/pytest ^
                    sh -c "py.test --verbose --junit-xml test-reports/results.xml sources/test_calc.py"
                    '''
                }
            }
            post {
                always {
                    junit 'test-reports/results.xml'
                }
            }
        }
        stage('Deliver') {
            steps {
                script {
                    // Pull the Docker image
                    bat 'docker pull cdrx/pyinstaller-linux:python3'
                    // Build the executable inside the Docker container
                    bat '''
                    docker run --rm ^
                    -v "%WORKSPACE%":/workspace ^
                    -w /workspace ^
                    cdrx/pyinstaller-linux:python3 ^
                    sh -c "pyinstaller --onefile sources/add2vals.py"
                    '''
                }
            }
            post {
                success {
                    archiveArtifacts 'dist/add2vals'
                }
            }
        }
    }
}
