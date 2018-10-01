pipeline {
    agent any
    stages{
        stage('Build'){
            steps {
              /* sh 'export M2_HOME=/opt/apache-maven'
               sh 'export PATH=$PATH:$M2_HOME/bin'
               sh 'mvn --version'*/
               sh '''
               echo "M2_HOME = ${M2_HOME}"
               mvn clean compile
               '''
            }
            post {
                success {
                    echo 'Now Archiving...'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }
    }
}
