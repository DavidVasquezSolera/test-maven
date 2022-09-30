pipeline { 
    agent any 
    stages {
        stage('Clean') { 
            steps { 
                bat "mvn clean"
            }
        }
        stage('Test'){
            steps {
                bat "mvn test"
            }
        }
        stage('Package') {
            steps {
                bat "mvn package"
            }
        }
        stage('Package') {
           steps {
               input "Do you want to save the changes?"
               junit "**/target/surefire-reports/TEST-*.xml"
               archive "target/*.jar"
           }
        }
    }
}
