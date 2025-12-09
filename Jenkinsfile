pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Hello World"'
                sh '''
                    echo "Multiline shell steps works too"
                    ls -lah
                '''
            }
        }
    }
    post {
        failure {
            mail to: 'stefanw70@hotmail.com',
             subject: "Failed Pipeline: ${currentBuild.fullDisplayName}",
             body: "Something is wrong with pipeline"
        }
        success {
            mail to: 'stefanw70@hotmail.com',
             subject: "Succeded Pipeline: ${currentBuild.fullDisplayName}",
             body: "Pipeline completed successfully"
        }
    }
}