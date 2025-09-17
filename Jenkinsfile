pipeline {
    agent any

    tools {
        jdk 'Java17'   // Имя JDK, настроенное в Jenkins Global Tools
        maven 'Maven3' // Имя Maven, настроенное в Jenkins Global Tools
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Neket27/Test.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Test') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploy step: здесь можно добавить деплой на сервер или Docker'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
