pipeline {
    agent any

    tools {
        maven "apache-maven-3.9.8"
        jdk "jdk-22"
    }

    stages {
        stage('Initialize'){
            steps{
                echo "PATH = ${apache-maven-3.9.8}/bin:${PATH}"
                echo "M2_HOME = /opt/maven"
            }
        }
        stage('Build') {
            steps {
                dir("/var/lib/jenkins/workspace/New_demo/my-app/") {
                sh 'mvn -B -DskipTests clean package'
                }
            
            }
        }
     }
    post {
       always {
          junit(
        allowEmptyResults: true,
        testResults: '*/test-reports/.xml'
      )
      }
   } 
}
