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
role_arn = arn:aws:iam::ACCOUNT:role/ec2
role_name = ec2
region= us-east-1
source_profile=default



[profile s3]
role_arn = arn:aws:iam::ACCOUNT:role/s3admin
role_name = s3admin
region= us-east-1
source_profile=default

```

### ~/.aws/credentials: store IAM > user > security credentials > access key > activate

```
[default]
aws_access_key_id = KEY 
aws_secret_access_key = SECRET
```

## manual setup
### assume role 
```
aws sts assume-role --role-arn arn:aws:iam::ACCOUNT:role/ec2 --role-session-name "fer-session"
export AWS_ACCESS_KEY_ID=
export AWS_SECRET_ACCESS_KEY=
export AWS_SESSION_TOKEN=

```

# IAM REMOTE SETUP
## LOGIN TO SERVER VIA SSH
### ssh : EC2 > left menu > instances > click instance ID > connect button > ssh client > copy example in terminal
```
ssh -i "(key_pem)" ec2-user@ec2(-server-hostname)
```

### aws configure credentials
```
aws configure
AWS Access Key ID [None]: (key)
AWS Secret Access Key [None]: (secret)
Default region name [None]: us-east-2
Default output format [None]: json
```

### aws cofigure profiles - nano
```
nano ~/(document location)
add the following info
[default]
region = (us-east-1)
output = (json)
[profile (profilename)]
role_arn = add arn
role_name = add name
region= (us-east-1)
source_profile=default
```


### aws test connection
```
aws sts get-caller-identity --profile (profile name)
aws sts assume-role --role-arn (arn) --role-session-name "****"
```

## deactivate user key or token: IAM > user > security credentials > access key > deactivate





