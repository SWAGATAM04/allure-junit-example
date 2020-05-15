pipeline {
    agent any
    stages {
        stage("Build") {
            steps {
                sh './mvnw clean verify'
            }
        }
        stage("Reports") {
            steps {
                allure results: [[path: 'target/allure-results']]
            }
        }
    }
    post {
        always {
            deleteDir()
        }
    }
}
