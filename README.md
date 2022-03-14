# Terraform AWS Resource to Service Authorization Mapping

*Disclaimer: this should not be considered as 100% valid data and must be reviewed before progressing.*

This repo tries to answer a question:
  
  > "Which AWS Terraform provider resources are related to a specific AWS service prefix, like *EC2:\**?"

It attempts to answer the question while mapping documentation from [AWS Terraform provider](https://registry.terraform.io/providers/hashicorp/aws/latest) to [AWS Service Authorization items](https://docs.aws.amazon.com/service-authorization/latest/reference/reference_policies_actions-resources-contextkeys.html#actions_table).

The results are stored in [dumps](dumps/) directory.

The latests parsed version: **[hashicorp/aws v4.5.0](https://registry.terraform.io/providers/hashicorp/aws/4.5.0)**

## Notebooks

- [Extracts data from the original sites](extract.ipynb)
- [Transforms the gathered data](transform.ipynb)

## Generated Files

- [AWS service prefix to Terraform resources](dumps/aws_action_to_tf_resource.json)
- [AWS service name to prefix mapping](dumps/aws_actions_name_to_prefix.json)
- [AWS service action references](dumps/aws_actions_reference.json)
- [AWS CloudFormation Resources References](dumps/aws_cf_resources_docs.json)
- [List of AWS CloudFormation Resources](dumps/aws_cf_resources.json)
- [AWS Terraform provider docs](dumps/aws_terraform_provider_docs.json)
- [List of AWS Terraform resources](dumps/aws_tf_resources.json)

---

## Items to Review

- [x] 'VPC': 'AWS Cloud9' - pointed to EC2
- [x] 'File System (FSx)': 'Amazon Elastic File System'
- [x] 'EventBridge (CloudWatch Events)': 'Amazon EventBridge Schemas'
- [x] 'ElasticSearch': 'Amazon ElastiCache'
- [X] 'Service Discovery': 'Application Discovery'
- [x] 'EFS': 'Amazon FSx'
- [x] 'S3 Control': 'AWS Control Tower'
- [x] 'Autoscaling Plans': 'AWS Savings Plans'
- [ ] DocumentDB': 'Amazon SimpleDB'
- [x] 'S3 Outposts': 'AWS Outposts'
- [x] 'Quantum Ledger Database (QLDB)': 'Amazon DynamoDB Accelerator (DAX)'

## Missing Service Mapping

- [ ] **DocumentDB** to AWS service prefix


## References
- [Terraform AWS provider](https://registry.terraform.io/providers/hashicorp/aws/latest/docs)
- [CloudFormation Resources Reference](https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/aws-template-resource-type-ref.html)
- [Service Authorization Reference](https://docs.aws.amazon.com/service-authorization/latest/reference/reference_policies_actions-resources-contextkeys.html)
