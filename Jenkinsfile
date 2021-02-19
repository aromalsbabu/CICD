pipeline{
//Directives
//Use any agent can be used to execute the pipeline, Allocate the executer and cleate a workspace for the pipeline 
agent any
//Tools to preinstall/Add the tool to the path.
 tools{
    maven 'maven'
 }
//Dynamically read the values from pom.xml. Must install "Pipeline Utility Plugin" in maven.
environment{
    ArtifactId = readMavenPom().getArtifactId()
    Version = readMavenPom().getVersion()
    Name = readMavenPom().getName()
    GroupId = readMavenPom().getGroupId()
}
//Stages in the pipeline
    stages{
        //Stage 1, build stage
        stage ('Build'){
            steps{
               sh 'mvn clean install package'
            }

        }
        //Stage to read values from pom.xml
        stage ('ReadMavenPom'){
            steps{
                echo "ArtifactId is ${ArtifactId}"
                echo "Version is ${Version}"
                echo "Name is ${Name}"
                echo "Name is ${GroupId}"   
            }
        }
        //Stage 2, Test stage
        stage ('Test'){
            steps{
                echo 'Testing!!!'
            }
        }
        //Stage 3, Upload to Nexus
        stage ('Upload'){
             steps{
              //  nexusArtifactUploader artifacts: [[artifactId: "${ArtifactId}", classifier: '', file: 'target/AromalDevOps-0.0.4-SNAPSHOT.war', type: 'war']], credentialsId:// //'215501f5-28a1-4b44-bba9-31dbffc5e0a7', groupId: "${GroupId}", nexusUrl: 'privateipv4address:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'Aromal-SNAPSHOT', version: "${Version}"
            echo "Upload to Nexus!!"
             }
            
        }
        stage ('Deploying'){
            steps{
                echo 'Installing!!!'
            }
        }


    }
}
