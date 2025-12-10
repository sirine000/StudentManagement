pipeline {
    agent any

    tools {
        jdk 'JAVA_HOME'       
        maven 'M2_HOME'       
    }

    triggers {
        cron('H/5 * * * *') 
    }

    stages {
        stage('Checkout') {
            steps {
              
                git branch: 'main',
                    url: 'https://github.com/sirine000/StudentManagement.git'
            }
        }

        stage('Clean & Build') {
            steps {
              
                sh 'mvn clean install'
            }
        }
    }

    post {
        success {
            echo 'Build terminé avec succès !'
        }
        failure {
            echo 'Le build a échoué.'
        }
    }
}
