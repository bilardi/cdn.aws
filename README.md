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
```

### Cloudformation
If you want to create your infrastructure by only awscli, follow this [README.md](https://github.com/bilardi/cdn.aws/infrastructure/awscli/README.md) or run
```sh
cd cds.aws/infrastructure/awscli/
more README.md
```

### Other tools
If you want to create your infrastructure another tool, see this [directory](https://github.com/bilardi/cdn.aws/infrastructure) or run
```sh
ls cds.aws/infrastructure/
```
where you'll find some examples with own README.md.

## License
This package is released under the MIT license.  See [LICENSE](LICENSE) for details.
