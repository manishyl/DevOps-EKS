# DevOps-EKS
CICD EKS

![image](https://github.com/user-attachments/assets/2e7307aa-53df-42f3-9881-d0eb86aba657)

1. Create ECR Resporitory
2. Create CodeCommit Repository
   Clone the git repository from Code Commit to local repository, during the process provide your git credentials generated to login to git repo
   git clone https://git-codecommit.us-east-1.amazonaws.com/v1/repos/eks-devops-nginx

   Commit code and Push to CodeCommit Repo. builspec.yml, Dockerfile , app1 and kube-manifests
   ```
   git status
   git add .
   git commit -am "1 Added all files"
   git push
   git status
   
   ```

3.  Create STS Assume IAM Role for CodeBuild to interact with AWS EKS
4.  Update EKS Cluster aws-auth ConfigMap with new role created in previous step
5.  Create CodePipeline
6.  Updae CodeBuild Role to have access to ECR full access and EKS kubectl role
