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
                    sudo ssh -i /var/lib/jenkins/node.pem -t -o StrictHostKeyChecking=no ubuntu@ec2-13-42-22-82.eu-west-2.compute.amazonaws.com

                
                    sudo rm -rf ~/node
                    sudo mkdir ~/node
                    cd ~/node
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