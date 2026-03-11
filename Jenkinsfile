pipeline {
    agent any

    tools {
    jdk 'JDK17'
}

    stages {
        stage('Welcome Stage') {
            steps {
                echo "Welcome to Pipeline"
            }
        }

        stage('Maven Build') {
            steps {
                bat 'mvn install'
                bat 'mvn clean install' // Includes test by default
            }
        }

        stage('Run Tests') {
            steps {
                echo "Running Unit Tests"
                // Optional: You can explicitly run 'mvn test' here
                bat 'mvn test'
            }
        }

       stage('Publish Test Results') {
    steps {
        junit allowEmptyResults: true, testResults: '**/target/surefire-reports/*.xml'
    }
}

        stage('Build Success') {
            steps {
                echo "Build Successful"
            }
        }
    }
}
