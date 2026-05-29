@Library('cicdlab-java') _

pipeline{
    agent {
        label 'ahmed-agent-01'
    }
    tools {
        jdk 'jdk-11'
        maven 'maven-382'
    }
    environment {
        dockerUsername = credentials("docker-username")
        dockerPassword = credentials("docker-password")
    }
    stages{
        stage("Build frist app by java"){
            steps{
                   script{
                   def obj = new edu.iti.mavenclass()
                   obj.install_mvn(package install -DskipTests)

                }
            }
        }
        stage("test frist app by java"){
            steps{
                script{
                   def obj = new edu.iti.mavenclass()
                   obj.test_mvn

                }
            }
        }
        stage("Archive frist app by java"){
            steps{
                archiveArtifacts artifacts: '**/*jar', followSymlinks: false
            }
        }
        stage("build docker image for app by java"){
            steps{
                  script{
                   def obj = new edu.iti.dockerclass()
                   obj.build("ahmediti/ahmed-java","v${Build_Number}")

                }
            }
        }
        stage(" docker login"){
            steps{
                  script{
                   def obj = new edu.iti.dockerclass()
                   obj.login("${dockerUsername}","${dockerPassword}")

                }
            }
        }
        
        stage("build push image for app by java"){
            steps{
                script{
                   def obj = new edu.iti.dockerclass()
                   obj.push("ahmediti/ahmed-java","v${Build_Number}")

                }
            }
        }
        
    }

}