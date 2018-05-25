
@Library('firstLibrary@master') _

import org.sample.GlobalVariables

pipeline{
    
    agent{
        label 'docker'
    }
    stages{
        stage('start'){
            steps{
                echo 'started'
            }
        }
        stage('testLib'){
            steps{
                sayHello 'Ajay'
                println GlobalVariables.name
            }
        }
        stage('Maven Build') {
            agent {
                docker {
                    image 'maven:3-alpine' 
                    label 'docker'
            } 
            steps {
                echo 'Hello, Maven'
                sh 'mvn --version'
            }
        }
    }
}
