# Create Policy
-----------

The Catio AWS wizard will take you through the following steps to set up the access policy.

Use the steps below to create the necessary policy for Catio to access your cloud environment resources.

This can be created using the AWS CLI or on the management console.

### Using the CLI:

1.  Download the [Catio_API_Access.json](https://gist.githubusercontent.com/jackcusick95/aefd0104c437ed56d662a95fbfaf2769/raw/d718b33053116aa039207be61aafdb746dc7c06d/Catio_API_Access.json) file. See the contents below.
2.  Use the following command to create the policy:

```
aws iam create-policy \
  --policy-name Catio_API_Access \
  --policy-document file://Catio_API_Access.json
```

### Using the Management Console:

Go to the [IAM > Policies](https://us-east-1.console.aws.amazon.com/iam/home?region=us-west-2#/policies) page and click on the "Create Policy" and click on the "JSON" editor to paste the content of the policy above in the UI. Follow through the next steps of naming to Catio_API_Access and create the policy.

### Catio API Access Policy

```json
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Sid": "VisualEditor0",
      "Effect": "Allow",
      "Action": [
        "ec2:DescribeInstances",
        "elasticloadbalancing:DescribeLoadBalancers",
        "cloudfront:GetDistribution",
        "kinesis:ListStreams",
        "eks:DescribeNodegroup",
        "mq:DescribeBroker",
        "dynamodb:DescribeTable",
        "route53:ListResourceRecordSets",
        "es:DescribeDomain",
        "eks:ListNodegroups",
        "lambda:ListFunctions",
        "lightsail:GetInstances",
        "sqs:GetQueueAttributes",
        "cognito-idp:ListUserPools",
        "ecs:DescribeClusters",
        "elasticloadbalancing:DescribeLoadBalancerAttributes",
        "eks:AccessKubernetesApi",
        "eks:DescribeCluster",
        "elasticloadbalancing:DescribeRules",
        "ecs:ListContainerInstances",
        "eks:ListClusters",
        "ec2:DescribeSubnets",
        "dynamodb:ListTables",
        "mq:ListBrokers",
        "ec2:DescribeRegions",
        "s3:ListBucketVersions",
        "sns:ListTopics",
        "ce:GetCostAndUsage",
        "s3:ListBucket",
        "ecs:ListServices",
        "elasticloadbalancing:DescribeListeners",
        "eks:ListUpdates",
        "rds:DescribeDBClusters",
        "rds:DescribeDBInstances",
        "ecs:DescribeServices",
        "ecs:DescribeContainerInstances",
        "ecs:ListClusters",
        "sqs:ListQueues",
        "sns:GetTopicAttributes",
        "elasticloadbalancing:DescribeTags",
        "route53:ListHostedZones",
        "kinesis:DescribeStream",
        "eks:ListFargateProfiles",
        "es:ListDomainNames",
        "s3:ListAllMyBuckets",
        "ec2:DescribeVpcs",
        "elasticloadbalancing:DescribeTargetHealth",
        "cloudfront:ListDistributions",
        "redshift:DescribeClusters",
        "elasticloadbalancing:DescribeTargetGroups",
        "elasticache:DescribeCacheClusters",
        "apigateway:GET",
        "autoscaling:DescribeAutoScalingGroups",
        "organizations:ListAccounts",
        "logs:StartQuery",
        "logs:StopQuery",
        "logs:GetQueryResults",
        "logs:DescribeQueries",
        "logs:DescribeLogStreams",
        "logs:DescribeLogGroups",
        "logs:GetLogEvents",
        "logs:FilterLogEvents",
        "securitylake:ListDataLakes",
        "macie2:ListClassificationJobs",
        "ses:ListIdentities",
        "access-analyzer:ListAnalyzers",
        "kafka:ListClustersV2",
        "fsx:DescribeFileSystems",
        "glacier:ListVaults",
        "ecr:DescribeRepositories",
        "amplify:ListApps",
        "mgn:ListApplications",
        "elasticmapreduce:ListClusters",
        "appsync:ListGraphqlApis",
        "appconfig:ListApplications",
        "athena:ListWorkGroups",
        "appstream:DescribeImages",
        "auditmanager:ListAssessments",
        "elasticfilesystem:DescribeFileSystems",
        "ec2:DescribeVolumes",
        "sagemaker:ListDomains",
        "sagemaker:ListApps",
        "ecr:DescribeImages",
        "athena:ListQueryExecutions",
        "workspaces:DescribeWorkspaces",
        "eks:DescribeFargateProfile",
        "ec2:DescribeTransitGateways",
        "codeartifact:ListRepositories",
        "application-autoscaling:DescribeScalingPolicies",
        "cognito-idp:DescribeUserPool",
        "sqs:listqueuetags",
        "dynamodb:ListTagsOfResource",
        "ecr:ListTagsForResource",
        "appstream:ListTagsForResource",
        "s3:GetBucketTagging",
        "SNS:ListTagsForResource",
        "route53:ListTagsForResource",
        "lambda:GetFunction",
        "acm:ListCertificates",
        "kms:ListKeys",
        "glue:GetDatabases",
        "cloudformation:ListStacks",
        "cloudformation:DescribeStacks",
        "kms:ListResourceTags",
        "codecommit:ListRepositories",
        "iam:GetAccountSummary",
        "codepipeline:ListPipelines",
        "ecs:ListTagsForResource",
        "workspaces:DescribeTags",
        "acm:ListTagsForCertificate",
        "codecommit:BatchGetRepositories",
        "codepipeline:ListTagsForResource",
        "codecommit:ListTagsForResource",
        "codepipeline:GetPipeline",
        "appstream:DescribeFleets",
        "codedeploy:ListApplications",
        "codedeploy:ListTagsForResource",
        "sqs:listqueuetags",
        "cognito-idp:DescribeUserPool",
        "lambda:ListEventSourceMappings",
        "s3:GetBucketNotification",
        "ec2:DescribeNatGateways",
        "codedeploy:GetApplication"
      ],
      "Resource": "*"
    }
  ]
}
```