
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
        stage('Build') {
            agent {
                docker {
                    image 'maven:3-alpine' 
                    label 'docker'
                }
            } 
            steps {
               build 'mvn'
               runCommand( command:'echo welcome' timeout:'1000' )
            }
        }
    }
}
