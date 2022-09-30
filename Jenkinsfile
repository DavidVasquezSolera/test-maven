pipeline { 
    agent any 
    stages {
        stage('Parallel Execution') { 
            steps { 
                parallel(
                    a: {
                        bat "mvn clean"
                    },
                    b: {
                        bat "mvn test"
                    },
                    c: {
                        bat "mvn package"
                    }
                )
            }
        }
        stage('Results') {
           steps {
               input "Do you want to save the changes?"
               junit "**/target/surefire-reports/TEST-*.xml"
               archive "target/*.jar"
           }
        }
    }
}
