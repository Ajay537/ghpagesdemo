
@Library('firstLibrary@master') _

import org.sample.GlobalVariables

pipeline{
    agent {
        docker {
            image 'maven:3-alpine' 
            label 'docker'
        }
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
            steps {
               build 'mvn'
               setEnv name:'build_na', path: 'aj'
                echo ${build_na}
            }
        }
    }
}
