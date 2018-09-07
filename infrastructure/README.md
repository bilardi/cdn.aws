# Commands for provisioning the infrastructure
```sh
grep your -R config/*
# edit your custom configuration and then
pip install sceptre
export AWS_PROFILE=your-account
sceptre validate-template production s3
sceptre launch-env production
```
