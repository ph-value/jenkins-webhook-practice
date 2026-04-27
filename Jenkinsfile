pipeline {
    agent any
    stages {
        stage('Deploy') {
            steps {
                echo 'pipeline-test 브랜치에서만 실행되는 Deploy ... '
            }
        }
        stage('Checkout') {
            steps {
                echo 'Check and check and check ...'
            }
        }
    }
    
    post {
        always {
            echo '파이프라인 종료'
        }
        success { 
            echo '성공적으로 완료됨'
        }
        failure { 
            echo '실패 발생'
        }
    }
}
