# circleci-orb-terraform

[![CircleCI Orb Version](https://img.shields.io/badge/endpoint.svg?url=https://badges.circleci.io/orb/suzuki-shunsuke/terraform)](https://circleci.com/orbs/registry/orb/suzuki-shunsuke/terraform)
[![CircleCI](https://circleci.com/gh/suzuki-shunsuke/circleci-orb-terraform.svg?style=svg)](https://circleci.com/gh/suzuki-shunsuke/circleci-orb-terraform)
[![GitHub last commit](https://img.shields.io/github/last-commit/suzuki-shunsuke/circleci-orb-terraform.svg)](https://github.com/suzuki-shunsuke/circleci-orb-terraform)
[![License](http://img.shields.io/badge/license-mit-blue.svg?style=flat-square)](https://raw.githubusercontent.com/suzuki-shunsuke/circleci-orb-terraform/master/LICENSE)

CircleCI Orb to lint and test and apply Terraform configuration.

## Sample repository

https://github.com/suzuki-shunsuke/example-circleci-orb-terraform

## How does this orb work?

You can construct the following pipeline for Terraform.

1. setup (checkout code and install tools such as [tfnotify](https://github.com/mercari/tfnotify), and [github-comment](https://github.com/suzuki-shunsuke/github-comment))
2. lint and test Terraform configuration
3. apply the Terraform configuration

The following screenshot represents multiple Terraform configuration which are managed at a monorepo are tested in parallel.

https://circleci.com/workflow-run/ed297905-f645-4ddb-8227-2dd8e07579b9

<p align="center">
  <img src="https://cdn.jsdelivr.net/gh/suzuki-shunsuke/artifact@master/circleci-orb-terraform/pipeline-diagram.png">
</p>

When it is failed to run `terraform fmt -check` or `terraform validate`, the result is posted by [github-comment](https://github.com/suzuki-shunsuke/github-comment).

https://github.com/suzuki-shunsuke/example-circleci-orb-terraform/pull/15#issuecomment-601552500

<p align="center">
  <img src="https://cdn.jsdelivr.net/gh/suzuki-shunsuke/artifact@master/circleci-orb-terraform/fmt-check-error.png">
</p>

https://github.com/suzuki-shunsuke/example-circleci-orb-terraform/pull/15#issuecomment-601552506

<p align="center">
  <img src="https://cdn.jsdelivr.net/gh/suzuki-shunsuke/artifact@master/circleci-orb-terraform/validate-error.png">
</p>

The results of `terraform plan` and `terraform apply` are posted by [tfnotify](https://github.com/mercari/tfnotify). Of course you can change the format of the comment by tfnotify's configuration.

https://github.com/suzuki-shunsuke/example-circleci-orb-terraform/pull/15#issuecomment-601553452

<p align="center">
  <img src="https://cdn.jsdelivr.net/gh/suzuki-shunsuke/artifact@master/circleci-orb-terraform/plan.png">
</p>

https://github.com/suzuki-shunsuke/example-circleci-orb-terraform/pull/16#issuecomment-601556085

<p align="center">
  <img src="https://cdn.jsdelivr.net/gh/suzuki-shunsuke/artifact@master/circleci-orb-terraform/apply.png">
</p>

## License

[MIT](LICENSE)
