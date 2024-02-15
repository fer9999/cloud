# S3 local setup
## create bucket: click in create bucket > select region > add bucket's name > click creat bucket 
## add files in buckets: select bucket > click on uploud button > click on add files > select file > click on upload button
### open files in bucket since terminal 
```
chmod 400 "url instance key"
aws s3 ls --profile s3
aws s3 ls --profile s3 (bucket's name)
aws s3 cp
aws s3 cp --profile s3 s3://(bucket's name)/(file's name) /tmp
cd /tmp
python3 -m http.server 8080
python3 -m http.server 8080 &
curl localhost:8080
```
