pipeline {
    agent {
        label 'testing_web_server'
    }
    
    stages {
        stage('cleaning old contents') { 
            steps {

                sh "sudo rm -rvf /var/www/html/*"
                sh "sudo rm -rvf /var/www/html/.git"
                
            }
        }
        stage('Cloning repo') { 
            steps {
                sh "sudo git clone https://github.com/TamangPemba/website.git /var/www/html/"
                // 
            }
        }
        stage('Reloading code') { 
            steps {
                sh "sudo systemctl reload httpd"
            }
        }
    }
}
