# CI-CD-pipeline-using-AWS
# What is CodeCommit?

CodeCommit is a managed source control service by AWS that allows users to store, manage, and version their source code and artifacts securely and at scale. It supports Git, integrates with other AWS services, enables collaboration through branch and merge workflows, and provides audit logs and compliance reports to meet regulatory requirements and track changes. Overall, CodeCommit provides developers with a reliable and efficient way to manage their codebase and set up a CI/CD pipeline for their software development projects.

# Task-01 :
# Set up a code repository on CodeCommit and clone it on your local.
Log in to the AWS Management Console and navigate to CodeCommit.
# Click on Create repository.


![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/0f579893-6bb8-460b-a8c0-963fcf40b35b)

Enter a name for your repository and click on 'Create'
![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/f29d9dbb-75f9-47a3-94ca-c5524fbb53c6)

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/e8d7e112-46d7-41f7-8fe9-b59097ab96f3)
The repository is successfully created.

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/75a814fa-3ef3-41df-bc3f-000ae177c402)
# You need to setup Git Credentials in your AWS IAM.
Go to IAM console

Click on Users in the left-hand menu, and then click on your username.

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/bbad2860-d1e9-40a5-9c13-54b2be83ab4a)
Scroll down to the Security credentials section.

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/9dba9736-4d37-402a-8d71-1c0d11002886)
Under security credentials, scroll down and come to 'HTTPS Git credentials for AWS CodeCommit' section, click on 'Generate credentials
![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/d61ddb97-e22c-455b-bc99-bd8c946a0c4c)

# Use those credentials in your local and then clone the repository from CodeCommit
In Code Commit, Go inside your repository that you created in above steps, in right-hand side click on 'Clone URL' and choose 'Clone HTTPS'.

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/ce54d94b-0723-40da-9074-e85946f52141)
# Open a terminal on your local machine.

Navigate to the directory where you want to clone the repository.

Run the following command:
'''git clone <your-codecommit-repo-clone-https-url>'''

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/3628dea8-bab8-4a5e-a6dd-dcbc3f5f651b)
# Task-02 :
Add a new file from local and commit to your local branch
Create a new file in the local repository directory.

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/12714954-8db3-441f-8a60-659e72c571cb)

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/c021be0d-f270-40c1-98bb-c6c1679da10e)

Push the local changes to CodeCommit repository.

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/186e654f-b777-4d4e-a791-75a5b856dc3d)

# Verify that the changes have been pushed to the CodeCommit repository:
Go to the code commit repository that you created earlier, you should see the new file listed in the repository's files.

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/049f21e5-07b0-4617-9b07-0bee19a34b42)

# Task-01 :
# Read about Buildspec file for Codebuild.

A Buildspec file is a YAML file that defines the build process for your CodeBuild project. It contains a series of commands that CodeBuild will execute to build and package your application.

# Create a simple index.html file in CodeCommit Repository.

you have to build the index.html using nginx server

Login to your AWS account by using valid credentials. Search CodeCommit from the search box and click on it. Click on Create repository. Enter mandatory details like the Repository name and Create a code commit repository.

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/ebb2854f-c801-40ea-9a8f-2dafe77bf60c)

You have a simple index.html file in your CodeCommit repository
![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/fb1cc97c-05c8-426d-b5bf-051b0a90f7d3)

# Task-02 :
# Add buildspec.yaml file to CodeCommit Repository and complete the build process.

Create a Buildspec file to build the file using an nginx server.

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/ed0af342-12bb-43b1-9827-4e87c1a66859)

Here's what each step of the build does:

version: 0.2 specifies the version of the Buildspec syntax we're using.
phases contains the build phases for our project.
install: Installs nginx on the build environment using the apt-get package manager.
build: Copies the index.html file to the default web root directory for nginx.
post_build: Performs any additional configuration for nginx, if necessary.
artifacts: Specifies the location of the index.html file to be included in the build artifact.

Save the file and commit the changes to the repository using the git add and git commit commands.

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/a647ab8d-faf7-4d84-a91b-16d1a70f208d)

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/eda3205a-8920-477d-a038-51f500780926)

You have a buildspec.yml and index.html file in your CodeCommit repository

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/13b0213c-2c06-4135-af92-a5ec8569bb1a)

# Create build project:
Go to the CodeBuild service. Click the "Create build project" button.

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/0ec3fdfb-3c7b-446f-8dd7-1e5a621ae838)

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/29463c81-fafe-4285-a598-f16bb498d70c)

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/9152fb76-9f23-40c3-8554-608720bfacf1)

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/ee44a9cb-d9f8-42ed-b5f3-d429b771bfa3)

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/3ee762d4-4bcd-43a0-a01a-59dd0d276c43)

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/b192c5a9-edf2-4ff5-8f51-51d34cc12e73)

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/807248de-90a8-4c6d-84d2-9b272fc566c4)

# To add artifacts to a CodeBuild project and store them in an S3 bucket.

Click on 'edit' and select 'Artifacts'.

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/45b94629-f65b-44df-86ee-651046aade9f)

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/5c7a0f4c-4773-4bc0-96e0-71116355cb5c)

# In Artifacts, select type Amazon S3 and select bucket name that you created in above step.
After the build process is complete, the artifacts will be uploaded to the specified S3 bucket location.

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/97912605-4d66-4182-b30a-0ccefeb17d36)

In buildspec.yml file, inside artifacts phase there is a location of file which is /var/www/html/index.html. you can check that folders and index.html file inside s3 bucket.

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/9c2322a9-f1d9-45d5-bbfb-aad8e8463b16)

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/da4c97c2-65a8-473d-b089-a0ea36f0d5a2)

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/579c736e-2644-47a0-8a0c-dbf8de16dbb6)

# You can see inside /var/www/html there is index.html file.
Click on 'index.html' file, below you can see properties of file.

Click on 'open' on right-hand side.

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/a3803424-16f3-4e97-a66d-83e3b4f25849)

# Here is an output of index.html file.

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/2dc68ec9-4e48-49c7-807d-5c477f227f05)

# Read about Appspec.yaml file for CodeDeploy.
The application specification file (AppSpec file) is a YAML -formatted or JSON-formatted file used by CodeDeploy to manage deployment. The AppSpec file for an EC2/On-Premises deployment must be named appspec. yml or appspec.yaml, unless you are performing a local deployment.

The appspec.yaml file is a configuration file that defines how the deployment should proceed. It specifies the deployment process, including which files should be deployed, where they should be deployed, and any scripts or hooks that should be executed during the deployment.

The appspec.yaml file typically includes the following sections:

version: This section specifies the version of the AppSpec file format being used.

os: This section specifies the operating system of the target instances.

files: This section specifies the source and destination locations of the files to be deployed.

hooks: This section specifies any scripts or hooks that should be executed during the deployment, such as scripts to stop and start the application.

The AppSpec file must be located in the root directory of the application source code and must be named “appspec.yml” or “appspec.yaml”. When you create a deployment group in CodeDeploy, you can specify the location of the AppSpec file in the deployment configuration.

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/ab8a2616-2b5f-4da9-a1c6-915cdedfca3a)

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/936072a9-f181-4a2e-b34c-cb9c7b1f3d32)

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/6375f2e6-0894-43c5-9338-22aed51c5a8c)

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/eb55a2cc-3503-4852-bf55-ccef801b48d3)

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/752e16de-c733-45c6-950b-b96e94517c7f)


# 2. Create a CodePipeline that gets the code from CodeCommit, Builds the code using CodeBuild and deploys it to a Deployment Group.
Go to the CodePipeline console. Click "Create pipeline."

Enter a name for your pipeline.

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/385a6551-95bf-4152-bfda-8774d8a38418)


Under "Source provider," choose "AWS CodeCommit."

Select the repository and branch you want to deploy.

Click "Next."

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/4f9ca28c-dd21-489c-8ff1-9b7f9ebc0e09)


Under "Build provider," choose "AWS CodeBuild."

Select "build project name."

Click "Next.

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/87cddf61-948a-4854-a4f6-44698dc89252)


Under "Deploy provider," choose "AWS CodeDeploy."

Select the deployment group you created earlier.

Click "Next."

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/0434863b-73a1-4298-ac24-93c5b1ee1f1e)


Review the pipeline settings and click "Create pipeline."

The pipeline will automatically trigger a build and deploy the new code to the EC2 instance.

Successfully created a CodePipeline that automates the deployment process.

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/8f60910c-27cd-4e69-aa40-7b47fb89c4a1)

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/d52443f2-63f7-43de-a95b-e8d4eb2e8d2d)

![image](https://github.com/chaudharyvishalrawat/CI-CD-pipeline-using-AWS/assets/104204831/03bcac96-9bd5-4e2a-be2a-ff9c513f8c6d)

# Thank you for reading!!
