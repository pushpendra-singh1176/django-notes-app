@Library('shared')_
pipeline{
    agent { label 'vinod'}
    
    stages{
        stage("Code clone"){
            steps{
                script {
                    sh "whoami"
                    clone("https://github.com/pushpendra-singh1176/django-notes-app.git","main")
                }
            }
        }
        stage("Code Build"){
            steps{
                script {
                    build("notes-app","latest","xerox2")
                }
            }
        }
        stage("Push to DockerHub"){
            steps{
                script {
                    dockerpush("notes-app","latest")
                }
            }
        }
        stage("Deploy"){
            steps{
                script {
                    deploy()
                }
            }
        }
        
    }
}
