pipeline {
    agent any

    stages {
        stage("Build") {
            steps {
                sh "mvn compile"
            }
        }

        stage("Test") {
            steps {
                wrap([$class: 'Xvfb', debug: true, displayName: 17, displayNameOffset: 0, timeout: 12]) {
                    sh "mvn test"
                }
            }
        }

        stage("Publish") {
            steps {
                testNG()
            }
        }
    }
}
