# Commands for provisioning the infrastructure
You need to modify the configuration files and to install awscli
```sh
grep your -R config/*
# edit your custom configuration and then
pip install awscli --upgrade --user
aws configuration --profile your-account
aws configure set region your-region --profile your-account
export AWS_PROFILE=your-account
```
If you don't save your custom configurations on a repository versioned, then copy all on s3
```sh
aws s3 cp . s3://your-custom-configurations-bucket/cdn.aws/ --recursive --exclude "*" --include "*.json" --include "*.yaml" --include "*yml" --profile your-account
```
If you have to modify it, then copy all on your local
```sh
aws s3 cp s3://your-custom-configurations-bucket/cdn.aws/ . --recursive --exclude "*" --include "*.json" --include "*.yaml" --include "*yml" --profile your-account
```
If you have to deploy for the first time your stacks
```sh
aws cloudformation create-stack --stack-name your-sns-stack-name --template-body file://./templates/production/sns.yaml --parameters file://./config/production/sns.json --profile your-account
aws cloudformation create-stack --stack-name your-s3-stack-name --template-body file://./templates/production/s3.yaml --parameters file://./config/production/s3.json --profile your-account
aws cloudformation create-stack --stack-name your-cloudwatch-stack-name --template-body file://./templates/production/cloudwatch.yaml --parameters file://./config/production/cloudwatch.json --profile your-account
```
If you have to update your stacks
```sh
aws cloudformation update-stack --stack-name your-sns-stack-name --template-body file://./templates/production/sns.yaml --parameters file://./config/production/sns.json --profile your-account
aws cloudformation update-stack --stack-name your-s3-stack-name --template-body file://./templates/production/s3.yaml --parameters file://./config/production/s3.json --profile your-account
aws cloudformation update-stack --stack-name your-cloudwatch-stack-name --template-body file://./templates/production/cloudwatch.yaml --parameters file://./config/production/cloudwatch.json --profile your-account
```
