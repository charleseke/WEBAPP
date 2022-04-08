pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'
    }

    stages {
        // Specify various stage with in stages

        // stage 1. Build
        stage ('Build'){
            steps {
                sh 'mvn clean install package'
            }
        }

        // Stage2 : Testing
        stage ('Test'){
            steps {
                echo ' testing......'

            }
        }

        // Stage 3 : Publish the artifacts to Nexu
        stage ('Publish to Nexus'){
            steps{
                nexusArtifactUploader artifacts: [[artifactId: 'VinayDevOpsLab', classifier: '', file: 'target/VinayDevOpsLab-0.0.9-SNAPSHOT.war', type: 'war']], credentialsId: 'e1c53d50-e242-470a-a870-1ff5523b8458', groupId: 'com.vinaysdevopslab', nexusUrl: '172.20.10.139:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'CharlesDevOpsLab-SNAPSHOT', version: '0.0.10-SNAPSHOT'
            }
        }

        // Stage3 : Deploying
        stage ('Deploy'){
            steps {
                echo ' deploying......'

            }
        }
                
    }

}