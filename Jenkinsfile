pipeline {
    agent any

    stages {
        stage('clone') {
            steps {
                git branch: 'feature/2026.06.18', url: 'https://github.com/Harishprathi/Calculator.git'
            }
        }
        
        stage('build') {
            steps {
                bat 'mvn install'
            }
        }
        
        stage('Test') {
            steps {
                bat 'mvn test'
            }
        }
        
        stage('Generated test results') {
            steps {
               junit 'target/surefire-reports/*.xml'
            }
        }
        
         stage('Generated artifactss') {
            steps {
              archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
            }
        }
        
        stage('deploy') {
            steps {
                echo 'deploy'
            }
        }
        
    }
}
