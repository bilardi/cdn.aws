# Commands for provisioning the infrastructure
```sh
grep your -R config/*
# edit your custom configuration and then
pip install awscli --upgrade --user
aws configuration --profile your-account
aws configure set region your-region --profile your-account
pip install sceptre
export AWS_PROFILE=your-account
sceptre validate production/s3
sceptre launch production
```
