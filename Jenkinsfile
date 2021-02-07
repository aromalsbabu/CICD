pipeline{
//Directives
//Use any agent can be used to execute the pipeline, Allocate the executer and cleate a workspace for the pipeline 
agent any
//Tools to preinstall/Add the tool to the path.
 tools{
    maven 'maven'
 }
//Stages in the pipeline
    stages{
        //Stage 1, build stage
        stage ('Build'){
            steps{
               sh 'mvn clean install package'
            }

        }
        //Stage 2, Test stage
        stage ('Test'){
            steps{
                echo 'Testing!!!'
            }
        }
        //Stage 3, Deploying
        stage ('Deploying'){
            steps{
                echo 'Installing!!!'
            }
        }


    }
}
