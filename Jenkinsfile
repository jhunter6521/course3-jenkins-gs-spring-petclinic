pipeline {
    
    agent any
    
    stages {
        stage("checkout") {
            steps{
                sh "ls"
                git branch:"main", url: "https://github.com/jhunter6521/course3-jenkins-gs-spring-petclinic"
                sh "ls"
            }
        }
        stage("build") {
            steps {
               sh "./mvnw package" 
            }
        }
        
        stage("capture") {
            steps {
                archiveArtifacts '**/target/*.jar'
                jacoco()
                junit '**/surefire-reports/*.xml'
            }
        }
    }
}
