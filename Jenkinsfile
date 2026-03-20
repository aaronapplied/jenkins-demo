pipeline {
    agent any

    stages {
        stage('检出代码') {
            steps {
                checkout scm
                sh 'ls -la'
            }
        }

        stage('环境信息') {
            steps {
                sh 'java -version'
                sh 'git --version'
                sh 'echo "分支：${GIT_BRANCH}"'
                sh 'echo "提交：${GIT_COMMIT}"'
            }
        }

        stage('模拟构建') {
            steps {
                sh 'echo "开始构建..."'
                sh 'sleep 2'
                sh 'echo "构建完成！"'
            }
        }

        stage('模拟测试') {
            steps {
                sh 'echo "运行测试..."'
                sh 'sleep 1'
                sh 'echo "测试通过！"'
            }
        }
    }

    post {
        success {
            echo "Pipeline 执行成功！构建号：${BUILD_NUMBER}"
        }
        failure {
            echo "Pipeline 执行失败，请检查日志。"
        }
        always {
            cleanWs()
        }
    }
}
Finished: SUCCESS
