pipeline {
    agent any
    stages {
        stage('Install') {
            steps {
                echo '===== Install Start ... ====='
                bat '"%PYTHON_EXE%" -m pip install pytest pytest-html'
            }
        }
        stage('Test') {
            steps {
                echo '===== Test Start ... ====='
                bat '"%PYTHON_EXE%" -m pytest tests --junitxml=reports/junit.xml --html=reports/report.html --self-contained-html'
            }
        }
    }

    post {
        always {
            echo '===== 파이프라인 종료 ====='
            junit 'reports/junit.xml'

            publishHTML(target: [
                allowMissing: false,
                alwaysLinkToLastBuild: true,
                keepAll: true,
                reportDir: 'reports',
                reportFiles: 'report.html',
                reportName: 'HTML Report'
            ])

        }
        success { 
            echo '===== 성공적으로 완료됨 ====='
        }
        failure { 
            echo '===== 실패 발생 ====='
        }
    }
}
