pipeline{
    tools {
        maven 'maven3.9'
    }
    stages{
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
