# AWS IAM Role-Based Service Access

<p align="center">
  <img src="https://img.shields.io/badge/AWS-IAM-orange?style=for-the-badge&logo=amazonaws" />
  <img src="https://img.shields.io/badge/Amazon-S3-569A31?style=for-the-badge&logo=amazons3&logoColor=white" />
  <img src="https://img.shields.io/badge/Amazon-EC2-FF9900?style=for-the-badge&logo=amazonec2&logoColor=white" />
  <img src="https://img.shields.io/badge/GitHub-Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white" />
  <img src="https://img.shields.io/badge/OIDC-Identity%20Provider-6f42c1?style=for-the-badge" />
</p>

<p align="center">
  Hands-on AWS IAM project focused on users, policies, roles, EC2 and S3 access.
</p>

---

## Project Workflow

```text
IAM User → Group → Policy → S3
EC2 → IAM Role → Policy → S3
GitHub → OIDC Identity Provider → IAM Role → AWS
```

## What I Built

• Created a private S3 bucket
• Created IAM User and Group
• Attached `AmazonS3ReadOnlyAccess`
• Tested permissions with IAM Policy Simulator
• Created an IAM Role for EC2
• Connected EC2 to S3 using the IAM Role
• Explored GitHub OIDC authentication with AWS

## EC2 → S3

The main working implementation:

```text
EC2
 ↓
IAM Role
 ↓
S3
```

After attaching the IAM Role to EC2, I verified S3 access using:

```bash
aws s3 ls
```

The EC2 instance accessed S3 without storing AWS Access Keys or Secret Keys.

## IAM Permission Test

| Action       | Result    |
| ------------ | --------- |
| GetObject    | ✅ Allowed |
| DeleteObject | ❌ Denied  |

This helped me understand how IAM policies control access to AWS resources.

## GitHub OIDC

I also explored GitHub OIDC to understand how GitHub Actions can authenticate with AWS without long-term credentials.

I successfully configured the Identity Provider and IAM trust relationship, but the GitHub Actions workflow kept failing during testing, so this part was not included in the final working implementation.

However, I deep-dived into the OIDC authentication flow and plan to implement it properly in another project.

## Tech Stack

<p>
  <img src="https://skillicons.dev/icons?i=aws,github,githubactions,linux" />
</p>

AWS IAM • Amazon S3 • Amazon EC2 • GitHub Actions • OIDC • AWS CLI • Linux

## Key Learnings

• IAM User → Human identity
• IAM Group → Manage users together
• IAM Policy → Define permissions
• IAM Role → Secure service access
• EC2 → S3 through IAM Role
• OIDC → Passwordless/long-term-credential-free authentication concept

## Project Post

Read the project walkthrough on LinkedIn:

🔗 [AWS IAM Role-Based Service Access Project](https://lnkd.in/p/gS7CxibU)

---

<p align="center">
  ☁️ Learn → Build → Test → Troubleshoot → Improve
</p>
