pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                sh 'rm -rf build'
                sh 'mkdir build'
                sh 'touch build/car.txt'
                sh 'echo "Chassis" > build/car.txt'
                sh 'echo "Engine" >> build/car.txt'
                sh 'echo "Body" >> build/car.txt'
            }
        }
        stage('Test') {
            steps{
                sh 'test -f build/car.txt'
                sh 'grep "Chassis" build/car.txt'
                sh 'grep "Engine" build/car.txt'
                sh 'grep "Body" build/car.txt'
            }
        }
        stage('Publish'){
            steps{
                archiveArtifacts artifacts: 'build/'
            }
        }
    }
}
