pipeline {
    agent any

    tools {
        maven 'maven_3_6_3'
        jdk 'JAVA_HOME' 
    }
    
    stages {
        
        stage ('Validation') {

            steps {
                withMaven(maven : 'maven_3_6_3') {
                    bat 'mvn validate'
                }
            }
        }
        
        stage ('Compilation') {

            steps {
                withMaven(maven : 'maven_3_6_3') {
                    bat 'mvn clean compile'
                }
            }
        }

        stage ('Testing Phade') {

            steps {
                withMaven(maven : 'maven_3_6_3') {
                    bat 'mvn test'
                }
            }
        }


        stage ('Deployment') {
            steps {
                withMaven(maven : 'maven_3_6_3') {
                    bat 'mvn install'
                }
            }
        }
    }
}
