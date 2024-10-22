pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                // Clone repository từ Git
                git url: 'https://github.com/HaDTM/C-ProgramData-Jenkins-.jenkins-workspace-Biometric-Admin-Auto-Date.git', branch: 'main'
            }
        }

        stage('Build') {
            steps {
                // Thực hiện lệnh build (tùy thuộc vào công cụ bạn đang sử dụng, ví dụ Maven)
                sh 'mvn clean package'  // Hoặc lệnh build khác nếu bạn không dùng Maven
            }
        }

        stage('Test') {
            steps {
                // Chạy test (có thể dùng JUnit, TestNG, hoặc các framework khác)
                sh 'mvn test'  // Hoặc lệnh test khác nếu bạn không dùng Maven
            }
        }

        stage('Deploy') {
            steps {
                // Triển khai ứng dụng (tùy thuộc vào môi trường và cách triển khai của bạn)
                echo 'Deploying application...' // Thay thế bằng lệnh thực tế để triển khai
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed.'
        }
    }
}
