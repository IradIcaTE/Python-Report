pipeline {
    agent { label "First" }
    
    stages {
        stage("Checkout") {
            steps {
                git url: "https://github.com/IradIcaTE/Python-Report.git", branch: "main"
            }
        }

        stage ("Run Python Script") {
            steps {
                sh 'python3 generate_report.py'
            }
        }

        stage ("Archive Report") {
            steps {
                archiveArtifacts artifacts: 'report.txt', onlyIfSuccessful: true
            }
        }
    }
}