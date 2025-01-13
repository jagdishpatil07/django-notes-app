@Library('Shared')_
pipeline {
    agent { label 'master' } // Ensure this matches the master node's label

    stages {
        stage("Code clone") {
            steps {
                sh "whoami"
                clone("https://github.com/jagdishpatil07/django-notes-app.git", "main")
            }
        }
        stage("Code Build") {
            steps {
                dockerbuild("notes-app", "latest")
            }
        }
        stage("Deploy") {
            steps {
                deploy()
            }
        }
    }
}

