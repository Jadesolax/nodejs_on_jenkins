pipeline {
    agent any
    stages{
        stage('testing'){
            steps{
            echo "this is testing"
            }
        }

        stage('running'){
            steps{
            echo "this is running"

            sh '''
                    sudo ssh -i /var/lib/jenkins/nodej.pem -t -o StrictHostKeyChecking=no ubuntu@ec2-3-8-203-58.eu-west-2.compute.amazonaws.com

                
                    sudo rm -rf ~/nodej
                    sudo mkdir ~/nodej
                    cd ~/nodej
                    sudo git init
                    sudo git remote add origin https://github.com/Jadesolax/nodejs_on_jenkins.git
                    sudo git pull origin master
                    sudo npm install
                    sudo npm run dev

                '''
            }
        }

        stage('production'){
            steps{
            echo "this is production"
            }
        }
    
    }
}