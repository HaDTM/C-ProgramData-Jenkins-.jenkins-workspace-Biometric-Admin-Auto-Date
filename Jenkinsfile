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
                // Thực hiện lệnh build
                script {
                    // Kiểm tra nếu có file pom.xml, nếu có thì sử dụng Maven
                    if (fileExists('pom.xml')) {
                        sh 'mvn clean package'
                    } else {
                        // Thay thế bằng lệnh build khác nếu không dùng Maven
                        echo 'No Maven project found, skipping build step.'
                    }
                }
            }
        }

        stage('Test') {
            steps {
                // Chạy test
                script {
                    // Kiểm tra nếu có file pom.xml, nếu có thì sử dụng Maven
                    if (fileExists('pom.xml')) {
                        sh 'mvn test'
                    } else {
                        // Thay thế bằng lệnh test khác nếu không dùng Maven
                        echo 'No Maven project found, skipping test step.'
                    }
                }
            }
        }

        stage('Deploy') {
            steps {
                // Triển khai ứng dụng
                echo 'Deploying application...' // Thay thế bằng lệnh thực tế để triển khai
                // Ví dụ lệnh deploy thực tế:
                // sh './deploy.sh'
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
        always {
            // Bước này sẽ chạy bất kể thành công hay thất bại
            echo 'Cleaning up resources...'
            // Thực hiện các bước cleanup nếu cần
     
