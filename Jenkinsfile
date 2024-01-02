pipeline {
    agent any
    stages {
        stage("checkout") {
            steps {
                git branch:'main', url: 'https://github.com/g0t4/course3-jenkins-gs-spring-petclinic'
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
                junit '**/target/surefire-reports/TEST*.xml'                
            }
        }        
    }
    
}
