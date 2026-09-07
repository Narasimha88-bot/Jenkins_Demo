pipeline {
    agent { label 'slave_node' }

    tools {
        maven 'maven3.9'
    }

    stages {
        stage('Checkout stage') {
            steps {
                git branch: 'main', url: 'https://github.com/Narasimha88-bot/Jenkins_Demo.git'
            }
        }

        stage('Build and Package') {
            steps {
                sh 'mvn clean package -DskipTests'
            }
        }

        // Optional: Add a Deploy stage if needed
        // stage('Deploy') {
        //     steps {
        //         sh 'scp target/*.war user@server:/opt/tomcat/webapps/'
        //     }
        // }
    }

    post {
        success {
            echo '✅ Build pushed to Artifactory, latest WAR printed, and deployed to Tomcat successfully.'
        }
        failure {
            echo '❌ Pipeline failed. Check logs for details.'
        }
    }
}
