# codebuild-simple-app
The pipeline consists of three phases: pre_build, build, and post_build.  

In the pre_build phase, the script connects to Amazon Elastic Container Registry (ECR) by running an AWS command and logging in with a command that retrieves the login password and uses it to authenticate. It also sets the repository URI and commit hash variables to be used later in the pipeline.  

In the build phase, the script starts by echoing the current date, then it proceeds to build a Docker image by using the current working directory as the context, and tagging it with the latest version and the build version.  

In the post_build phase, the script echoes that the build is complete, then it pushes the built images to the ECR repository and tags them with the latest version and the build version. it also creates an image definition file (imagedefinitions.json) with the image URI and name of the application.  

Finally, the pipeline will output an artifacts file 'imagedefinitions.json' which can be used to deploy the image.
