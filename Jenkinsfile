pipeline {
    agent any

    tools {
        
        maven "MVN-3.8.4"
    }

    stages {
        stage('Build') {
            steps {
               
                git "https://github.com/udayaDJ/maven-app.git"

                
                sh "mvn -Dmaven.test.failure.ignore=true clean deploy"

               
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
