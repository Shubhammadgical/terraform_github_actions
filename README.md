# Automate Terraform with GitHub Actions

This article would guide us ho to Automate Terraform with GitHub Actions.

I took inspiration from this [article](https://developer.hashicorp.com/terraform/tutorials/automation/github-actions?in=terraform%2Fautomation) and the code is explained in these videos [part-1](https://shorthillstech-my.sharepoint.com/personal/kapil_jain_shorthillstech_com/_layouts/15/onedrive.aspx?ga=1&id=%2Fpersonal%2Fkapil%5Fjain%5Fshorthillstech%5Fcom%2FDocuments%2FTraining%2FDevOps%2FProjects%2FAutomate%20Terraform%20with%20GitHub%20Actions%20%2D%20ShubhamChaurasia%2Emp4&parent=%2Fpersonal%2Fkapil%5Fjain%5Fshorthillstech%5Fcom%2FDocuments%2FTraining%2FDevOps%2FProjects), [part-2](https://shorthillstech-my.sharepoint.com/personal/kapil_jain_shorthillstech_com/_layouts/15/onedrive.aspx?ga=1&id=%2Fpersonal%2Fkapil%5Fjain%5Fshorthillstech%5Fcom%2FDocuments%2FTraining%2FDevOps%2FProjects%2FAutomate%20Terraform%20with%20GitHub%20Actions%28part%20%2D%202%29%20%2D%20ShubhamChaurasia%2Emp4&parent=%2Fpersonal%2Fkapil%5Fjain%5Fshorthillstech%5Fcom%2FDocuments%2FTraining%2FDevOps%2FProjects), and [part-3](https://shorthillstech-my.sharepoint.com/personal/kapil_jain_shorthillstech_com/_layouts/15/onedrive.aspx?ga=1&id=%2Fpersonal%2Fkapil%5Fjain%5Fshorthillstech%5Fcom%2FDocuments%2FTraining%2FDevOps%2FProjects%2FAutomate%20Terraform%20with%20GitHub%20Actions%28part%20%2D%203%29%20%2D%20ShubhamChaurasia%2Emp4&parent=%2Fpersonal%2Fkapil%5Fjain%5Fshorthillstech%5Fcom%2FDocuments%2FTraining%2FDevOps%2FProjects). 

- Prerequisites
  - Terraform Cloud Account

  - AWS Account

  - GitHub Account

# Set up Terraform Cloud

1. Create a new workflow in Terraform Cloud Account.

![workspace](https://user-images.githubusercontent.com/101810595/207565202-fa56527a-2191-42c5-a065-1fe3356de23e.gif)

2. Add below Variables in terraform Cloud and make it env and sensitive.

![Screenshot_20221214_153315](https://user-images.githubusercontent.com/101810595/207566329-d9b01e5e-97ad-46ca-9f6b-147026c40bbe.png)

3. Finally, go to the Tokens page in your Terraform Cloud User Settings. Click on "Create an API token" and generate an API token named GitHub Actions.

![token](https://user-images.githubusercontent.com/101810595/207566240-2388ce12-f310-43ba-b206-6ce9df8d874b.gif)

# Set up a GitHub repository

1. Creake new repository, navigate to "Settings" then "Secrets". Create a new secret named TF_API_TOKEN, setting the Terraform Cloud API token you created in the previous step as the value.

![secrets](https://user-images.githubusercontent.com/101810595/207567248-5356eb9e-f985-419e-a3fc-89c53e9f589c.gif)

2. Copy .github, .gitignore, and main.tf file from this [repo](https://github.com/hashicorp/learn-terraform-github-actions)  in your repo.

3. Create a new branch in your repo name update-tfc-backend.

4. Open main.tf file and give your organization name in line no. 15 which you created in Terraform Cloud Account. 

5. Run below commands:

```
git add .
git commit -m 'Point backend to correct TFC org and workspace'
git push
```

6. Generate a pull request from the update-tfc-backend branch. From the base repository drop-down, choose your repository and main branch.

7. Navigate to your pull request in GitHub. Your PR will trigger the Terraform Actions workflow. When the workflow completes, it will add a comment with the outcome of each step and a speculative plan.

![review](https://user-images.githubusercontent.com/101810595/207570548-6159d231-21b8-4844-9aa8-8ffbab839431.gif)

8. You can track the status of the apply job through GitHub Actions or Terraform Cloud. In GitHub, go to "Actions", then select the pull request you just merged.

Then, click on the "Terraform" workflow. Notice how the "Terraform Plan", "Update Pull Request" and "Terraform Plan Status" steps have been skipped.

Expand the "Terraform Apply" step. Terraform should have created the two resources and displayed the EC2 instance's address.

![apply](https://user-images.githubusercontent.com/101810595/207571170-7581f16d-927d-46dc-ae31-0359f95c1eca.gif)

9. Verify that the EC2 instance is publicly available. Remember to replace the address below with the one in Terraform's output. Run below command in your terminal.

```
curl ec2-54-187-5-177.us-west-2.compute.amazonaws.com:8080
```

# Steps to Destroy resources

1. Open Terraform Cloud, then open your workspace.

2. Click Workspace settings, then click in the Destruction and Deletion.

3. Click Queue destroy plan button. Provide workspace name then then click button. Then click conform and apply button.

![Screenshot_20221214_161353](https://user-images.githubusercontent.com/101810595/207574396-9a121d8d-2332-4950-814f-edb00d380c20.png)

4. For deleting workspace click Delete from Terraform Cloud button in Destruction and Deletion section and follow same steps.





