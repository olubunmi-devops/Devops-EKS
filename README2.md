# EKS cluster setup with terraform
1. Create an EC2 instance,SSH and perform the neccesary updates.
2. Required tools are installed and running
![image](https://github.com/user-attachments/assets/bab88562-2595-453a-af69-f33d60df4d01)
3. Clone your repository to your local
![image](https://github.com/user-attachments/assets/dd2131dc-c7ed-40a5-8689-c287af121ce0)
4.  Navigate to the appropriate folder and execute the the required commands.
5.  Do Helm create docker-cicd
![image](https://github.com/user-attachments/assets/8b11ece2-77ca-4e4f-9f8c-38d5e836eb3a)
By default, helm will initialise a chart that deploys nginx. In our case, we need to deploy our own image not nginx. To do this, edit the values.yaml file in line 7, to 11, edit to the code snippet below:
![image](https://github.com/user-attachments/assets/54b66d94-82e5-45ef-ad1c-8e5cd87a52ca)
The code block, removes nginx image and replaces it with username/imagename. Don’t worry about it being invalid the plan is to get the pipeline to automatically fill in the username, image name, and tag name so just let the username and imagename be like that, don’t edit it to your own.
![image](https://github.com/user-attachments/assets/e8a9ecb7-2e8f-43b0-ae76-480be254a6a3)
6.Create EKS cluster using Terraform.If you already have an EKS cluster running in AWS you can use, you can skip this part and jump straight to the GitHub actions section. Else, navigate to /terraform folder in the codebase directory and execute the command:
Note: Ensure you have set up your AWS CLI and access keys on your local machine before executing the terraform commands.
terraform init
Next, apply the terraform script:
terraform apply --auto-approve
![image](https://github.com/user-attachments/assets/ec0ab08d-1360-4d2f-a50b-64ba80a90df1)
