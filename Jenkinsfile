pipeline{
    agent any
    stages {
        stage("sonar quality check"){
            agent{
                docker {
                    image 'openjdk:11'
                }
            }
            steps{
                script{
                    withSonarQubeEnv(credentialsId: '6944a876-d735-490e-86b2-86c586733793') {
                        sh 'chmod +x gradlew'
                        sh './gradlew sonarqube'
                                                      }
                }
            }
        }
    }
}