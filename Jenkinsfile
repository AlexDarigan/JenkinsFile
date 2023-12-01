pipeline {
    agent any

    stages {
        stage('Fetch') {
            steps {
            // Fetch repository
                git branch: 'main', credentialsId: 'Github', url: 'https://github.com/AlexDarigan/studentAttendance'
            }
        }
        stage('Build') {
            steps {
                 // Compile files with JUnit package
                sh 'javac -d bin src/Student.java src/StudentTest.java -cp ./bin/junit-platform-console-standalone-1.9.3.jar'
            }
        }
        stage('Test') {
            steps {
                // Test class
                sh 'java -jar bin/junit-platform-console-standalone-1.9.3.jar --class-path bin --select-class StudentTest'
            }
        }
        stage('Package') {
            steps {
                // Packaging files into jar
                sh 'jar cvf bin/Student.jar bin/*.class'
            }
        }
    }
}
