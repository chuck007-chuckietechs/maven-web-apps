@Library('chuckietech_shared_library') _

pipeline{
    agent any
    
    tools{
        maven "Maven-3.9.5"
    }
    
    stages{
        
        stage('Git Clone'){
            steps{
               git branch: 'main', credentialsId: 'GIT-Credentials', url: 'https://github.com/chuck007-chuckietechs/maven-web-apps.git'
               //gitClone()
            }
        }
        
        stage('Build'){
            steps{
              mavenBuild()
            }
        }
        
        stage('Code Review'){
            steps{
              sonarQube()
            }
        }
    }
}