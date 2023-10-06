# Jenkins Pipeline: Check Java and Maven Installation

This Jenkins pipeline checks for the installation of Java and Maven on the build agent and sets the build result accordingly. It ensures that your build environment has the required dependencies before proceeding with further tasks.

## Pipeline Stages

### Check Java
This stage verifies whether Java is installed on the build agent. If Java is found, it sets the current build result to 'SUCCESS'. If Java is not installed, it sets the build result to 'FAILURE' and throws an error.

### Check Maven
This stage checks for the installation of Apache Maven on the build agent. Similar to the Java stage, if Maven is installed, it sets the current build result to 'SUCCESS'. If Maven is not found, it sets the build result to 'FAILURE' and throws an error.

### Final
In the final stage, the pipeline checks the overall build result. If both Java and Maven were installed successfully, it prints 'Everything is installed.' Otherwise, it indicates that something is missing in the build environment.

## Usage
1. Create a Jenkins pipeline job.
2. In the pipeline configuration, select "Pipeline script from SCM" as the pipeline definition.
3. Specify the repository and path to this `Jenkinsfile`.
4. Save the configuration and run the pipeline.

The pipeline will perform the checks and provide feedback on the installation status of Java and Maven.

Please make sure that the Jenkins agent running this pipeline has Java and Maven installed or adjust the pipeline script to use a different build agent if needed.
