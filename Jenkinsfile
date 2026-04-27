pipeline {
    agent any
    stages {
        stage('Install') {
            steps {
                echo '===== Install Start ... ====='
                bat '"%PYTHON_EXE%" -m pip install pytest'
            }
        }
        stage('Test') {
            steps {
                echo '===== Test Start ... ====='
                bat '"%PYTHON_EXE%" -m pytest tests --junitxml=reports/junit.xml'
            }
        }
    }

    post {
        always {
            echo '===== 파이프라인 종료 ====='
            junit 'reports/junit.xml'

        }
        success { 
            echo '===== 성공적으로 완료됨 ====='
        }
        failure { 
            echo '===== 실패 발생 ====='
        }
    }
}
