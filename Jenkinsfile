pipeline {
   agent any
   stages {
        stage("checkout") {
            steps {
                git branch:'main', url: 'https://github.com/l-const/course3-jenkins-gs-spring-petclinic'
            }
            
         }

        stage("build") {
            steps {
                sh "./mvnw package"
            }
        }
   
        stage("capture") {
             // **/taget/*.jar
            steps {
                archiveArtifacts '**/target/*.jar'
                junit '**/target/surefire-reports/TEST*xml'
                jacoco() 
            } 
           
        }
   }    
  
   post {
       always {
           echo "Post body"
       }
   }
}