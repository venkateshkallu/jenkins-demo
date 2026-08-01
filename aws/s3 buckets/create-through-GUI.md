# AWS CLI Installation and Amazon S3 Bucket Management

## Objective

Learn how to:

- Install AWS CLI
- Configure AWS CLI
- Create S3 Buckets using AWS Console
- Create S3 Buckets using AWS CLI
- Verify Bucket Creation

---
## Install AWS CLI
```bash
Install unzip
sudo apt install unzip -y
curl "https://awscli.amazonaws.com/awscli-exe-linux-x86_64.zip" -o "awscliv2.zip"
unzip awscliv2.zip
sudo ./aws/install
aws --version
```

Expected Output:

```bash
aws-cli/2.x.x
```

---

## Configure AWS CLI

Run:

```bash
aws configure
```

Provide:

```text
AWS Access Key ID
AWS Secret Access Key
Region
Output Format
```

Example:

```text
AWS Access Key ID: ****************
AWS Secret Access Key: ****************
Default Region: ap-south-1
Default Output Format: json
```

### Screenshot

![AWS CLI Configuration](screenshots/configure-cli.png)

---

## Step 3: Create S3 Bucket Using AWS Console

1. Login to AWS Console
2. Navigate to S3
3. Click Create Bucket
4. Enter Bucket Name
5. Select Region
6. Create Bucket

### Screenshot

![Create Bucket GUI](screenshots/create-bucket-gui.png)

---

## Step 4: Create S3 Bucket Using AWS CLI

Command:

```bash
aws s3 mb s3://venkatesh-demo-bucket
```

Expected Output:

```bash
make_bucket: venkatesh-demo-bucket
```

### Screenshot

![Create Bucket CLI](screenshots/create-bucket-cli.png)

---

## Step 5: Verify Bucket

List Buckets:

```bash
aws s3 ls
```

Example:

```bash
2026-06-20 venkatesh-demo-bucket
```

### Screenshot

![List Buckets](screenshots/list-buckets.png)

---

## Key Learnings

- AWS CLI Installation
- AWS CLI Configuration
- IAM Access Keys
- S3 Bucket Creation
- S3 Bucket Management using CLI