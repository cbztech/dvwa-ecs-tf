<!-- BEGIN_TF_DOCS -->
## Requirements

No requirements.

## Providers

| Name | Version |
|------|---------|
| <a name="provider_aws"></a> [aws](#provider\_aws) | 4.20.0 |

## Modules

| Name | Source | Version |
|------|--------|---------|
| <a name="module_aws_vpc"></a> [aws\_vpc](#module\_aws\_vpc) | terraform-aws-modules/vpc/aws | 3.14.2 |
| <a name="module_public_subnet_sg"></a> [public\_subnet\_sg](#module\_public\_subnet\_sg) | terraform-aws-modules/security-group/aws | 4.9.0 |

## Resources

| Name | Type |
|------|------|
| [aws_cloudwatch_log_group.dvwa](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/cloudwatch_log_group) | resource |
| [aws_ecs_cluster.dvwa_cluster](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ecs_cluster) | resource |
| [aws_ecs_service.dvwa](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ecs_service) | resource |
| [aws_ecs_task_definition.dvwa](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/ecs_task_definition) | resource |
| [aws_iam_role.dvwa_task_execution_role](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_role) | resource |
| [aws_iam_role_policy_attachment.ecs_task_execution_role](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/resources/iam_role_policy_attachment) | resource |
| [aws_iam_policy.ecs_task_execution_role](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/iam_policy) | data source |
| [aws_iam_policy_document.ecs_task_assume_role](https://registry.terraform.io/providers/hashicorp/aws/latest/docs/data-sources/iam_policy_document) | data source |

## Inputs

| Name | Description | Type | Default | Required |
|------|-------------|------|---------|:--------:|
| <a name="input_cluster_name"></a> [cluster\_name](#input\_cluster\_name) | ECS Cluster | `string` | `"dvwa-cluster"` | no |
| <a name="input_cw_log_group"></a> [cw\_log\_group](#input\_cw\_log\_group) | ECS Service | `string` | `"/ecs/dvwa"` | no |
| <a name="input_ecs_role_name"></a> [ecs\_role\_name](#input\_ecs\_role\_name) | n/a | `string` | `"dvwa-task-execution-role"` | no |
| <a name="input_ecs_svc_name"></a> [ecs\_svc\_name](#input\_ecs\_svc\_name) | n/a | `string` | `"dvwa"` | no |
| <a name="input_ecs_task_family"></a> [ecs\_task\_family](#input\_ecs\_task\_family) | n/a | `string` | `"dvwa"` | no |
| <a name="input_owner"></a> [owner](#input\_owner) | n/a | `string` | n/a | yes |
| <a name="input_public_subnet_desc"></a> [public\_subnet\_desc](#input\_public\_subnet\_desc) | n/a | `string` | `"Security group for the public subnet"` | no |
| <a name="input_public_subnet_egress_cidr"></a> [public\_subnet\_egress\_cidr](#input\_public\_subnet\_egress\_cidr) | n/a | `list(any)` | <pre>[<br>  "0.0.0.0/0"<br>]</pre> | no |
| <a name="input_public_subnet_egress_rules"></a> [public\_subnet\_egress\_rules](#input\_public\_subnet\_egress\_rules) | n/a | `list(any)` | <pre>[<br>  "all-all"<br>]</pre> | no |
| <a name="input_public_subnet_ingress_cidr"></a> [public\_subnet\_ingress\_cidr](#input\_public\_subnet\_ingress\_cidr) | Add the ip address(es) that need(s) to access this ecs task in cidr format | `list(any)` | n/a | yes |
| <a name="input_public_subnet_ingress_rules"></a> [public\_subnet\_ingress\_rules](#input\_public\_subnet\_ingress\_rules) | n/a | `list(any)` | <pre>[<br>  "http-80-tcp"<br>]</pre> | no |
| <a name="input_public_subnet_name"></a> [public\_subnet\_name](#input\_public\_subnet\_name) | Security Group | `string` | `"public-subnet-sg"` | no |
| <a name="input_region"></a> [region](#input\_region) | n/a | `string` | `"us-east-1"` | no |
| <a name="input_vpc_azs"></a> [vpc\_azs](#input\_vpc\_azs) | n/a | `list(any)` | <pre>[<br>  "us-east-1a",<br>  "us-east-1b"<br>]</pre> | no |
| <a name="input_vpc_cidr"></a> [vpc\_cidr](#input\_vpc\_cidr) | n/a | `string` | `"10.0.0.0/16"` | no |
| <a name="input_vpc_name"></a> [vpc\_name](#input\_vpc\_name) | VPC Vars | `string` | `"dvwa_vpc"` | no |
| <a name="input_vpc_public_subnets"></a> [vpc\_public\_subnets](#input\_vpc\_public\_subnets) | n/a | `list(any)` | <pre>[<br>  "10.0.1.0/24",<br>  "10.0.2.0/24"<br>]</pre> | no |

## Outputs

No outputs.
<!-- END_TF_DOCS -->