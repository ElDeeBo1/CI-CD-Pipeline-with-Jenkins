pipeline{
    agent {
        label 'ahmed-agent-01'
    }
    tools {
        jdk 'jdk-11'
        maven 'maven-354'
    }
    environment {
        dockerUsername = Credentials("docker-username")
        dockerPassword = Credentials("docker-password")
    }
    stages{
        stage("Build frist app by java"){
            steps{
                sh "mvn package install -DskipTests"
            }
        }
        stage("test frist app by java"){
            steps{
                sh "mvn test"
            }
        }
        stage("Archive frist app by java"){
            steps{
                archiveArtifacts artifacts: '**/*jar', followSymlinks: false
            }
        }
        stage(" docker login"){
            steps{
                sh "docker login -u ${dockerUsername} -p ${dockerPassword}"
            }
        }
        stage("build docker image for app by java"){
            steps{
                sh "docker build -t frist-app:v1 ."
            }
        }
        // stage("build push image for app by java"){
        //     steps{
        //         sh "docker push frist-app:v1"
        //     }
        // }
        
    }

}