# Group Management with IAM in AWS

## Overview

When managing access in Amazon Web Services, assigning permissions directly to individual users does not scale well.  
IAM groups allow you to manage permissions once and apply them consistently across multiple users.

In this walkthrough, I demonstrate how **IAM group-based permissions** work by granting **read-only access to Amazon S3** and validating it through real user login testing.

---

## Step 1: Create IAM Users (DevUser1 and DevUser2)

1. Navigate to **IAM → Users → Create user**
2. Create two users:
   - `DevUser1`
   - `DevUser2`
3. Enable **AWS Management Console access**
4. Set a **custom password**
5. Complete user creation

---

## Step 2: Create an IAM Group Named `Developers`

1. Go to **IAM → User groups**
2. Click **Create group**
3. Enter the group name:Developers  

---

## Step 3: Add Users to the Developers Group

1. While creating the `Developers` group, select:
- `DevUser1`
- `DevUser2`
2. Add both users to the group

---

## Step 4: Attach `AmazonS3ReadOnlyAccess` Policy to the Group

1. In **Attach permissions policies**
2. Search for:
3. Select the policy
4. Complete group creation

---

## Step 5: Log In as DevUser1 and Verify S3 Read Access

1. Log out from the admin account
2. Sign in using **DevUser1** credentials
3. Navigate to **Amazon S3**

### Result

- S3 buckets are visible
- Bucket names, regions, and metadata can be viewed

---

## Step 6: Attempt to Upload a File (Expected Failure)

1. Open any S3 bucket
2. Click **Upload**
3. Attempt to upload a file

### Result

- Upload fails with **Access Denied**
- Error indicates insufficient permissions

This happens because the `AmazonS3ReadOnlyAccess` policy does **not** include:

- `s3:PutObject`
- `s3:DeleteObject`
- Any write-level permissions

---

## Key Takeaways

- IAM groups simplify access management at scale
- Permissions should be attached to **groups**, not individual users
- AWS managed policies are predictable and safe for controlled access
- Always validate permissions by logging in as the actual user
- Read-only access provides visibility without modification rights

