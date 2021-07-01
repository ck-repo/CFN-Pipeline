# CFN-Pipeline

Repo for the creation of a AWS CodePipeline implementation that provides the following functionality:

- Ability to create/update CloudFormation templates in the "templates" folder and push those changes to the GitHub Source branch to test if the stack deployment succeeds in the London and Frankfurt regions using the Taskcat tool
- Source Stage: webhook starts the pipeline and downloads Git repo artifact
- Build/Test Stage: performs Linting and Taskcat testing (deploys stacks, deletes stacks and creation of a HTML report in S3)
- Deploy Stage: if tests are successful a Lambda function is invoked to git merge the Source branch into the Release branch ready for release 

High Level Overview Diagram

![image](https://user-images.githubusercontent.com/54940429/124094140-6617b280-da50-11eb-97be-2e01b4b41213.png)

Note: CloudFormation template deployment not covered by this pipeline, this is a CloudFormation testing pipeline. 
