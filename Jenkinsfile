pipeline {
    agent any
    
    environment {
        EMAIL_RECIPIENT = 'alphatushar1912@gmail.com'
        USER_EMAIL = 'alphatushar1912@gmail.com'
    }
    
    stages {
        stage('Build Application') {
            steps {
                echo 'Initiating build process...'
            }
            post {
                always {
                    mail to: NOTIFY_EMAIL,
                         subject: 'Build Process Finished',
                         body: 'The build phase has been completed. Please check Jenkins logs for more details.'
                }
            }
        }
        
        stage('Execute Tests') {
            steps {
                echo 'Running unit and integration tests...'
            }
            post {
                always {
                    mail to: NOTIFY_EMAIL,
                         subject: 'Testing Phase Finished',
                         body: 'Unit and integration tests have been executed. Refer to logs for insights.'
                }
            }
        }
        
        stage('Code Review') {
            steps {
                echo 'Performing static code analysis...'
            }
            post {
                always {
                    mail to: NOTIFY_EMAIL,
                         subject: 'Code Review Completed',
                         body: 'Static code analysis has been completed. Review logs for more details.'
                }
            }
        }
        
        stage('Security Evaluation') {
            steps {
                echo 'Conducting security scans...'
            }
            post {
                always {
                    mail to: NOTIFY_EMAIL,
                         subject: 'Security Evaluation Done',
                         body: 'Security scanning has been performed. Check logs for outcomes.'
                }
            }
        }
        
        stage('Staging Release') {
            steps {
                echo 'Deploying application to staging...'
            }
            post {
                always {
                    mail to: NOTIFY_EMAIL,
                         subject: 'Staging Deployment Completed',
                         body: 'Application has been deployed to staging. Review logs for details.'
                }
            }
        }
        
        stage('Staging Tests') {
            steps {
                echo 'Executing tests on staging environment...'
            }
            post {
                always {
                    mail to: NOTIFY_EMAIL,
                         subject: 'Staging Tests Completed',
                         body: 'Tests on the staging environment have finished. Check logs for more info.'
                }
            }
        }
        
        stage('Production Deployment') {
            steps {
                echo 'Deploying to production environment...'
            }
            post {
                always {
                    mail to: NOTIFY_EMAIL,
                         subject: 'Production Deployment Completed',
                         body: 'Deployment to production has been executed. Review Jenkins logs for confirmation.'
                }
            }
        }
    }
    
    post {
        success {
            echo 'Pipeline executed successfully!'
            mail to: NOTIFY_EMAIL,
                 subject: 'Pipeline Execution Successful',
                 body: 'The entire pipeline has been completed successfully!'
        }
        failure {
            echo 'Pipeline execution failed. Investigate logs for more details.'
            mail to: NOTIFY_EMAIL,
                 subject: 'Pipeline Execution Failed',
                 body: 'The pipeline encountered an error. Check Jenkins logs for debugging.'
        }
    }
}
