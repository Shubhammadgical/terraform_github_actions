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
















