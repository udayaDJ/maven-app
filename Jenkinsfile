pipeline {
    agent any

    tools {
        
        maven "M3"
    }

    stages {
        stage('Build') {
            steps {
               
                git "https://github.com/udayaDJ/maven-app.git"

                
                sh "mvn -Dmaven.test.failure.ignore=true clean package"

               
            }

            post {
                
                success {
                    junit '**/target/surefire-reports/TEST-*.xml'
                    archiveArtifacts 'target/*.jar'
                }
            }
        }
    }
}
