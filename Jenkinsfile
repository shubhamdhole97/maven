pipeline {
         agent any
         stages {
             stage('Clone repository') {
                 steps {
                     git 'https://github.com/shubhamdhole97/maven.git'
                 }
             }
             stage('Build Maven Project') {
                 steps {
                     sh 'mvn clean package'
                 }
             }
             stage('Build Docker Image') {
                 steps {
                     sh 'docker build -t myapp .'
                 }
             }
             stage('Deploy to Docker') {
                 steps {
                     sh 'docker run -d -p 8080:8080 myapp'
                 }
             }
         }
     }
