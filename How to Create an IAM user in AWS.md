# How to Create an IAM User in AWS – Step-by-Step Guide

When working with AWS, it’s best practice not to use the root account for daily operations.  
Instead, you should create an IAM (Identity and Access Management) user with appropriate permissions.

In this article, I’ll walk through how I created an admin-level IAM user that can access all AWS services — similar to the root user but with better security and control.

---

## Step 1: Open the IAM Console

1. Sign in to the AWS Management Console using your root account.  
2. Navigate to IAM → Users.  
3. Click Create user.
# How to Create an IAM User in AWS – Step-by-Step Guide

When working with AWS, it’s best practice not to use the root account for daily operations.  
Instead, you should create an IAM (Identity and Access Management) user with appropriate permissions.

In this article, I’ll walk through how I created an admin-level IAM user that can access all AWS services — similar to the root user but with better security and control.

---

## Step 1: Open the IAM Console

1. Sign in to the AWS Management Console using your root account.  
2. Navigate to IAM → Users.  
3. Click Create user.



---

## Step 2: Specify User Details

In the User details section:

• Enter a username — I used userAdmin.  
• Enable “Provide user access to the AWS Management Console.”  
• Choose Custom password and create a strong password.  
• Enable the option “User must create a new password at next sign-in.”

This ensures security while allowing controlled access for other administrators or developers.



---

## Step 3: Assign Permissions

Now, assign permissions to define what the user can do in AWS.

• Choose Attach policies directly.  
• Search for and select Administrator Access from the policy list.

This policy grants full access to all AWS services such as EC2, S3, RDS, Lambda, IAM, and more essentially providing the same operational privileges as the root account (except for billing settings).



---

## Step 4: Review and Create

Before finalizing:

• Review all details including username, console access, and attached policies.  
• Once confirmed, click Create user.



---

## Step 5: Retrieve Login Credentials

After creation, AWS provides:

• Sign-in URL for the console  
• Username  
• Temporary password  

You can either download the credentials as a .csv file or email them secur



---

## Step 2: Specify User Details

In the User details section:

• Enter a username — I used userAdmin.  
• Enable “Provide user access to the AWS Management Console.”  
• Choose Custom password and create a strong password.  
• Enable the option “User must create a new password at next sign-in.”

This ensures security while allowing controlled access for other administrators or developers.



---

## Step 3: Assign Permissions

Now, assign permissions to define what the user can do in AWS.

• Choose Attach policies directly.  
• Search for and select Administrator Access from the policy list.

This policy grants full access to all AWS services such as EC2, S3, RDS, Lambda, IAM, and more essentially providing the same operational privileges as the root account (except for billing settings).



---

## Step 4: Review and Create

Before finalizing:

• Review all details including username, console access, and attached policies.  
• Once confirmed, click Create user.



---

## Step 5: Retrieve Login Credentials

After creation, AWS provides:

• Sign-in URL for the console  
• Username  
• Temporary password  

You can either download the credentials as a .csv file or email them securely to the new user.

Why Create IAM Users Instead of Using the Root Account?

The root user has unrestricted control over your AWS account — including billing and support — which makes it risky to use regularly.
Creating IAM users provides better governance, monitoring, and security.
## Benefits of using IAM users:
•	Improved security with least-privilege access.  
•	Easier access tracking via CloudTrail logs.  
•	Safer daily operations.  
•	Multi-user management without exposing root credentials.  
## Final Thoughts
Creating IAM users is one of the most fundamental steps in AWS account setup.
By assigning roles and permissions carefully, you can maintain full control over your resources while keeping your environment secure.
The root account should only be used for account-level tasks (like enabling billing or MFA), while daily work should happen through IAM users with AdministratorAccess.

