@Library('Shared')_
pipeline{
    agent { label 'sam'}
    
    stages{
        stage("Code clone"){
            steps{
            clone("https://github.com/SameerG16/Django-notes-app.git","main")
            }
        }
        stage("Code Build"){
            steps{
            dockerbuild("notes-app","latest")
            }
        }
        stage("Push to DockerHub"){
            steps{
                dockerpush("dockerHubCreds","notes-app","latest")
            }
        }
        stage("Deploy"){
            steps{
                deploy()
            }
        }
        
    }
}
