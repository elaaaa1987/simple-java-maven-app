pipeline {
    agent none
     stages {
        stage("Fix the permission issue") {
            
            agent any
            
            steps {
                sh "sudo chown root:elaaaa1987 /run/docker.sock"
            }
       }
       
       stage('Pull Image') {
        agent {
           docker {
            image 'maven:3.6.3-jdk-8' 
            args '-v /root/.m2:/root/.m2'
           }
        }
      }
      stage('Build') {
         steps {
            sh 'mvn -B -DskipTests clean package'
         }
      }
      
     
     }
}
