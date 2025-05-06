pipeline {
    agent any

    tools {
        jdk 'jdk-17'
        maven 'maven-3'
    }

    stages {
        stage('Clonar Repo') {
            steps {
                git url: 'https://github.com/rricardob/war.git', branch: 'main'
            }
        }

        stage('Compilar y Validar') {
            steps {
                sh 'mvn clean verify'
            }
        }
    }

    post {
        success {
            echo '✅ Build completado con éxito'
        }
        failure {
            echo '❌ Falló el build. Revisar pruebas o checkstyle.'
        }
    }
}
