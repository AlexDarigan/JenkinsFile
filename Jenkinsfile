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
                 // Compile student class file
                sh 'javac -d bin src/Student.java'
                sh 'jar cvf bin/Student.jar bin/Student.class'
            }
        }
    }
}




