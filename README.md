# cdn.aws
The repository contains all that you need to manage your content delivery network in an AWS account
* cloudformation templates of each object
* guideline to create all

## Prerequisite
* an AWS account, in this repository called **your-account**
* a bucket for coping cloudformation templates, in this repository called **your-cloudformation-templates-bucket** (*)

If you don't save your custom configurations on a repository versioned
* a bucket for coping custom configurations, in this repository called **your-custom-configurations-bucket** (*)

(*) see [bilardi/common.aws](https://github.com/bilardi/common.aws) for details.

## Usage
```sh
pip install awscli --upgrade --user
aws configuration --profile your-account
git clone https://github.com/bilardi/cds.aws.git
cd cds.aws/infrastructure/
more README.md
# and if you don't save your custom configurations on a repository versioned, then copy all on s3
aws s3 cp . s3://your-custom-configurations-bucket/cdn.aws/ --recursive --exclude "*" --include "*.json" --include "*.yaml" --include "*yml" --profile your-account
# and if you have to modify it, then copy all on your local
aws s3 cp s3://your-custom-configurations-bucket/cdn.aws/ . --recursive --exclude "*" --include "*.json" --include "*.yaml" --include "*yml" --profile your-account
```
