node{

    stage('clone'){

        git branch: 'feature/2026.06.18', url: 'https://github.com/Harishprathi/Calculator.git'
    }

    stage('build'){
        bat 'mvn install'
    }

    stage('test'){

        bat 'mvn test'
    }

    stage ('Generated test results'){

        junit 'target/surefire-reports/*.xml'
    }

    stage ('Generated artifacts'){

        archiveArtifacts artifacts: 'target/*.jar', followSymlinks: false
    }

    stage('deploy'){

        echo 'deploy'
    }
}