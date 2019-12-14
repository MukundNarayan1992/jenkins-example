pipeline {
    agent any


    stages {
        stage('SCM Checkout'){
          git 'https://github.com/MukundNarayan1992/jenkins-example'
        }
  }
    {
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'Localmaven') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'Localmaven') {
                    sh 'mvn test'
                }
            }
        }


        stage ('install Stage') {
            steps {
                withMaven(maven : 'Localmaven') {
                    sh 'mvn install'
                }
            }
        }

         stage ('deploy to tocat') {
             steps {
                 sshagent(['c4314358-27ee-4704-859a-44ddcb0fc88b']) {
                 sh 'scp -o StrictHostKeyChecking=no target/*.jar ec2-user@172.31.42.125:/var/lib/tomcat/webapps/'
      }
             }
   }
}
}
