pipeline {
    agent any

    stages {
        stage(checkout){
            steps{
                 git branch: 'main', url: 'https://github.com/Sumagowdav/Jenkins.git'
            }
        }
        stage('Hello') {
            steps {
                echo 'Hello World'
            }
        }
    }
}
