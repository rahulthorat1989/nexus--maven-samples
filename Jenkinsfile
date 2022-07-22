pipeline{
    agent any
    environment {
        PATH = "$PATH:/opt/maven/bin"
    }
    stages{
        stage("code Build"){
            steps{
                sh 'mvn clean package'
            }
        }
        stage("Sonarqube analysis"){
            steps{
                script{
                withSonarQubeEnv('sonarqube') {
                     sh 'mvn sonar:sonar' 
                  }
                }
            }
        }
    }
    post{
        always{
            echo "========always========"
        }
        success{
            echo "========pipeline executed successfully ========"
        }
        failure{
            echo "========pipeline execution failed========"
        }
    }
}
