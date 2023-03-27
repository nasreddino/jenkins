pipeline {
    agent any 
    stages {
        stage('Clone the repo') {
            steps {
                echo 'clone the repo'
                sh 'rm -fr jenkins'
                sh 'git clone https://github.com/nasreddino/jenkins.git'
            }
        }
        stage('push repo to remote host') {
            steps {
                echo 'connect to remote host and pull down the latest version'
                sh 'ssh hakuuuna@192.168.11.109 sudo git -C /var/www/html pull'
   }
        }
        stage('Check website is up') {
            steps {
                echo 'Check website is up'
                sh 'curl -Is 192.168.11.109 | head -n 1'
            }
        }
    }
}
