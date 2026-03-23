# Terraform + GitHub Actions + AWS S3 Website

Deploy a static website to **AWS S3** using **Terraform** and **GitHub Actions**.

## Setup

1. Configure AWS CLI with an IAM user (`AmazonS3FullAccess`).
2. Add `.gitignore`:

```
terraform/.terraform/
*.tfstate
*.tfstate.*
terraform.tfvars
.terraform.lock.hcl
```

3. Initialize & apply Terraform:

```bash
cd terraform
terraform init
terraform apply
```

4. Push to GitHub — GitHub Actions deploys `website/` to S3.

## GitHub Secrets

| Name | Value |
|------|-------|
| AWS_ACCESS_KEY_ID | IAM access key |
| AWS_SECRET_ACCESS_KEY | IAM secret key |
| BUCKET_NAME | Terraform bucket name |

## Website URL

After deployment:

```
http://<your-bucket>.s3-website-us-east-1.amazonaws.com
```