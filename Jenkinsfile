pipeline {
    agent label 'slave_node'
    tools {
        maven 'maven3.9'
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', 
                url: 'https://github.com/Narasimha88-bot/Jenkins_Demo.git'
            }

    }
    stage ('build'){
        steps {
            sh 'mvn clean package -DskipTests'
        }

    }

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
