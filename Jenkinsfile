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
}
}
