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
        
        stage ('test') {
            steps {
                withMaven(jdk: 'localJDK', maven: 'localmaven') {
                    sh 'mvn test'
                }
            }
        }
    }
}
