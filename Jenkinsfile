pipeline { 
    tools{
	jdk 'java1.8'
	maven 'maven_new'
    }
    agent any 
    stages {
        stage('Compile') { 
            steps {
                //withMaven(maven : 'apache-maven-3.6.0'){
                        sh "mvn compile"
                }
            }
        }
	stage('Code Review'){
           steps {
                //withMaven(maven : 'apache-maven-3.6.0'){
                        sh "mvn pmd:pmd"
                }

            }
        }
        stage('Unit Testing'){
            steps {
                //withMaven(maven : 'apache-maven-3.6.0'){
                        sh "mvn test"
                }

            }
        }
        stage('Code Coverage'){
            steps {
                //withMaven(maven : 'apache-maven-3.6.0'){
                        sh "mvn cobertura:cobertura -D cobertura.reports.format=xml"
                }

            }
        }
	stage('Package'){
            steps {
                //withMaven(maven : 'apache-maven-3.6.0'){
                        sh "mvn package"
                }

            }
        }
        //stage('Deploy') {
          //  steps {
            //   withMaven(maven : 'apache-maven-3.6.0'){
              //          sh "mvn deploy"
                //}

            //}
        //}
    }
}
