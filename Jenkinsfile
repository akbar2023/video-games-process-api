pipeline {
    agent any

    stages {
        stage('Munit Test') {
            steps {
                echo 'Testing..'
                bat 'mvn clean test'
            }
        }
        stage('Build') {
            steps {
                echo 'Building..'
                bat 'mvn clean install'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying to cloudHub...'
                bat 'mvn clean deploy -DmuleDeploy -DskipTests -Dmule.version=4.4.0 -Danypoint.username=akbar_khan2 -Danypoint.password=Mymulesoft@20 -Denv=Sandbox -Dappname=prc-videogames-api -Dbusiness=cap -DvCore=Micro -Dworkers=1'
                echo 'Deployed...'
            }
        }
    }
}