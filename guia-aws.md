# IAM local setup
## important commands 
```
aws sts get-caller-identity
aws configure
aws sts assume-role
```

## important files 
### ~/.aws/config: store profiles 

```
[profile ec2]
role_arn = arn:aws:iam::169680684171:role/ec2
role_name = ec2
region= us-east-1
source_profile=default



[profile s3]
role_arn = arn:aws:iam::169680684171:role/s3admin
role_name = s3admin
region= us-east-1
source_profile=default

```

### ~/.aws/credentials: store IAM > user > security credentials > token > activate

```
[default]
aws_access_key_id = KEY 
aws_secret_access_key = SECRET
```

## manual setup
### assume role 
```
aws sts assume-role --role-arn arn:aws:iam::169680684171:role/ec2 --role-session-name "fer-session"
export AWS_ACCESS_KEY_ID=
export AWS_SECRET_ACCESS_KEY=
export AWS_SESSION_TOKEN=

```


