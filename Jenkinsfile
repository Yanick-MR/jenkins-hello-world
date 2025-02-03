pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M399" and add it to the path.
        maven "M399"
    }
    
    // stages {
    //     stage ('Echo version'){
    //         steps{
    //             sh 'echo Print Maven Verion'
    //             sh 'mvn -version'
    //         }
    //     }
    // }
    stages {
        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                //sh 'export GIT_SSL_NO_VERIFY=false'
                //git 'https://gitlab-vmware-devops/learninggroup/jenkins-hello-world.git'

                // Run Maven on a Unix agent.
                sh "mvn clean package -DskipTests=true"

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }
        }    
        stage('Unit test'){
            steps{
                sh "mvn test"
            }
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
}
