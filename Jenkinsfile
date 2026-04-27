pipeline {
    agent any
    stages {
        stage('Debug') {
            steps {
                bat 'where python'
                bat 'python --version'
            }
        }
    }
    
    post {
        always {
            echo '===== 파이프라인 종료 ====='
        }
        success { 
            echo '===== 성공적으로 완료됨 ====='
        }
        failure { 
            echo '===== 실패 발생 ====='
        }
    }
}
