pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M398"
    }

    stages {
        stage ('Echo Version')
        {
            steps {
                sh 'echo print Maven Version'
                sh 'mvn -version'
            }
        }
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
               // git branch: 'main', url: 'https://github.com/Sandeepthesun/jenkins-hello-world'

                // Run Maven package cmd.
                sh "mvn clean package -DskipTests=true"

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }

            // post {
            //     // If Maven was able to run the tests, even if some of the test
            //     // failed, record the test results and archive the jar file.
            //     success {
            //         junit '**/target/surefire-reports/TEST-*.xml'
            //         archiveArtifacts 'target/*.jar'
            //     }
            // }
        }
        stage ('Unit Test') {
            steps{
                script {

                    for (int 1 = 0 ; i < 60 ; i++){
                    echo "${i + 1}"
                    sleep 1
                    }
                    
                    sh "mvn test"
                }
            }
        }
    }
}
