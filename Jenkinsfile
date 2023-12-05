pipeline {
    agent any

    stages {
        stage('Fetch') {
            steps {
            // Fetch repository
                git branch: 'main', credentialsId: 'githubId', url: 'https://github.com/AlexDarigan/studentAttendance'
            }
        }
        stage('Build') {
            steps {
                 // Compile files with JUnit package (There is no DSL for javac so we invoke shell instead)
                sh 'javac -d bin src/Student.java src/StudentTest.java --class-path ./lib/junit-platform-console-standalone-1.9.3.jar'
            }
        }
        stage('Test') {
            steps {
                sh 'java -jar lib/junit-platform-console-standalone-1.9.3.jar --class-path bin --select-class StudentTest'
            }
        }
    }
}