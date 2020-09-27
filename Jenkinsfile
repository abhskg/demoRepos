pipeline {
    agent any

    stages {
        
        stage ('Validation') {

            steps {
                withMaven(maven : 'maven_3_6_3') {
                    sh 'mvn validate'
                }
            }
        }
        
        stage ('Compilation') {

            steps {
                withMaven(maven : 'maven_3_6_3') {
                    sh 'mvn clean compile'
                }
            }
        }

        stage ('Testing Phade') {

            steps {
                withMaven(maven : 'maven_3_6_3') {
                    sh 'mvn test'
                }
            }
        }


        stage ('Deployment') {
            steps {
                withMaven(maven : 'maven_3_6_3') {
                    sh 'mvn deploy'
                }
            }
        }
    }
}
