# ecs-codedeploy-blue-green
Terraform module to perform Blue/Green deployments in ECS using CodeDeploy

<!-- BEGIN_TF_DOCS -->
## Requirements

| Name | Version |
|------|---------|
| <a name="requirement_terraform"></a> [terraform](#requirement\_terraform) | >= 1.0 |
| <a name="requirement_aws"></a> [aws](#requirement\_aws) | >= 4.0 |
| <a name="requirement_local"></a> [local](#requirement\_local) | >= 2.4.0 |

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | >= 4.0 |
| <a name="provider_local"></a> [local](#provider\_local) | >= 2.4.0 |
| <a name="provider_null"></a> [null](#provider\_null) | n/a |

## Modules

No modules.

## Resources

| Name | Type |
|------|------|
| [aws_codedeploy_app.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/codedeploy_app) | resource |
| [aws_codedeploy_deployment_group.this](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/codedeploy_deployment_group) | resource |
| [aws_iam_role.codedeploy_role](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_role) | resource |
| [aws_iam_role_policy_attachment.AWSCodeDeployRole](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_role_policy_attachment) | resource |
| [aws_iam_role_policy_attachment.AWSCodeDeployRoleForECS](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_role_policy_attachment) | resource |
| [local_file.deploy_script](https://registry.terraform.io/providers/hashicorp/local/latest/docs/resources/file) | resource |
| [null_resource.start_deploy](https://registry.terraform.io/providers/hashicorp/null/latest/docs/resources/resource) | resource |
| [aws_iam_policy_document.assume_role_code_deploy](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/iam_policy_document) | data source |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_alb_blue_target_group_name"></a> [alb\_blue\_target\_group\_name](#input\_alb\_blue\_target\_group\_name) | ALB Blue target group name | `string` | n/a | yes |
| <a name="input_alb_green_target_group_name"></a> [alb\_green\_target\_group\_name](#input\_alb\_green\_target\_group\_name) | ALB Green target group name | `string` | n/a | yes |
| <a name="input_alb_prod_listener_arns"></a> [alb\_prod\_listener\_arns](#input\_alb\_prod\_listener\_arns) | List of Arns of ALB Pod listners | `list(string)` | n/a | yes |
| <a name="input_alb_test_listener_arns"></a> [alb\_test\_listener\_arns](#input\_alb\_test\_listener\_arns) | List of Arns of ALB Test listners | `list(string)` | n/a | yes |
| <a name="input_codedeploy_application_name"></a> [codedeploy\_application\_name](#input\_codedeploy\_application\_name) | CodeDeploy Application name | `string` | n/a | yes |
| <a name="input_codedeploy_role_name"></a> [codedeploy\_role\_name](#input\_codedeploy\_role\_name) | CodeDeploy IAM Role name | `string` | n/a | yes |
| <a name="input_container_name"></a> [container\_name](#input\_container\_name) | Container name | `string` | n/a | yes |
| <a name="input_container_port"></a> [container\_port](#input\_container\_port) | Container port | `number` | n/a | yes |
| <a name="input_deployment_config_name"></a> [deployment\_config\_name](#input\_deployment\_config\_name) | CodeDeploy Deployment Config name | `string` | `"CodeDeployDefault.ECSAllAtOnce"` | no |
| <a name="input_deployment_group_name"></a> [deployment\_group\_name](#input\_deployment\_group\_name) | CodeDeploy Deployment group name | `string` | n/a | yes |
| <a name="input_ecs_cluster_name"></a> [ecs\_cluster\_name](#input\_ecs\_cluster\_name) | ECS Cluster name | `string` | n/a | yes |
| <a name="input_ecs_service_name"></a> [ecs\_service\_name](#input\_ecs\_service\_name) | ECS Service name | `string` | n/a | yes |
| <a name="input_ecs_task_def_arn"></a> [ecs\_task\_def\_arn](#input\_ecs\_task\_def\_arn) | ECS Task definition Arn | `string` | n/a | yes |
| <a name="input_old_tasks_termination_wait_time"></a> [old\_tasks\_termination\_wait\_time](#input\_old\_tasks\_termination\_wait\_time) | Old ECS task termination wait time in minutes | `number` | n/a | yes |

## Outputs

No outputs.
<!-- END_TF_DOCS -->