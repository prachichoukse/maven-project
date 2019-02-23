pipeline {
    agent any
    stages{
        stage('Build'){
            steps {
               bat 'mvn clean package'
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
	Stage('Deploy to Staging'){
		Steps{
		    build job: 'deploy-to-staging'	
		}
	}
    }
}