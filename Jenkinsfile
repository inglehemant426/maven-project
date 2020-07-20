pipeline {
    agent any
    stages {
        
        stage ('scm checkout') {
            steps {
                git branch: 'master', url: 'https://github.com/inglehemant426/maven-project'
            }
        }
        
        stage ('compile source code') {
            steps {
                withMaven(jdk: 'localJDK', maven: 'localmaven') {
                    sh 'mvn compile'
                }
            }
        }
        
        /*stage ('test') {
            steps {
                withMaven(jdk: 'localJDK', maven: 'localmaven') {
                    sh 'mvn test'
                }
            }
        }*/
        
        stage ('build') {
            steps {
                withMaven(jdk: 'localJDK', maven: 'localmaven') {
                    sh 'mvn package'
                }
            }
        }
        
        /*stage ('deploy to tomcat server') {
            steps {
               sshagent(['deploytomcat']) {
                    sh 'scp -o StrictHostKeyChecking=no */target/*.war ec2-user@172.31.86.233:/var/lib/tomcat/webapps'
                }
            }
        }*/
    }
}
