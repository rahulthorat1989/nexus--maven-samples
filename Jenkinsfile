pipeline{
    agent any
    stages{
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
