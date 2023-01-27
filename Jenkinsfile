pipeline {
    agent any
    stages {
        stage('git'){
            steps{
                git branch: 'app', url: 'https://github.com/krishank98/aws-terraform-cicd-java-springboot-working'
            }
        }
        stage('build') {
            steps {
                sh '/usr/local/sdkman/candidates/maven/current/bin/mvn install -DskipTests'
            }
        }
        stage('compose'){
            steps{
                sh 'cd docker/compose/ && /workspaces/aws-terraform-cicd-java-springboot-working/docker-compose up'
            }
        }
    }
}
