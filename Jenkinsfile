pipeline {
   agent any
   stages {

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