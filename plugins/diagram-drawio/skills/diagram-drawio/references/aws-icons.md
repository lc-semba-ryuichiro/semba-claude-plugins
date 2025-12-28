# AWS アイコン定義

draw\.ioでAWSアーキテクチャ図を作成する際のアイコンstyle定義。

## 目次

- [使用方法](#使用方法)
- [Compute](#compute)
  - [EC2](#ec2)
  - [Lambda](#lambda)
  - [ECS](#ecs)
  - [Fargate](#fargate)
- [Storage](#storage)
  - [S3](#s3)
  - [EBS](#ebs)
  - [EFS](#efs)
- [Database](#database)
  - [RDS](#rds)
  - [Aurora](#aurora)
  - [DynamoDB](#dynamodb)
  - [ElastiCache](#elasticache)
- [Networking](#networking)
  - [VPC](#vpc)
  - [Subnet (Public)](#subnet-public)
  - [Subnet (Private)](#subnet-private)
  - [ALB (Application Load Balancer)](#alb-application-load-balancer)
  - [CloudFront](#cloudfront)
  - [API Gateway](#api-gateway)
  - [Route 53](#route-53)
- [Application Integration](#application-integration)
  - [SQS](#sqs)
  - [SNS](#sns)
  - [EventBridge](#eventbridge)
  - [Step Functions](#step-functions)
- [Security](#security)
  - [IAM](#iam)
  - [Cognito](#cognito)
  - [Secrets Manager](#secrets-manager)
- [Management](#management)
  - [CloudWatch](#cloudwatch)
  - [CloudFormation](#cloudformation)
- [外部アクター](#外部アクター)
  - [User](#user)
  - [Users](#users)
  - [Internet](#internet)
- [AWS色カテゴリ](#aws色カテゴリ)
- [注意事項](#注意事項)

## 使用方法

draw\.ioには公式AWSアイコンライブラリが含まれている。
shape属性で `mxgraph.aws4.*` を指定することで利用可能。

***

## Compute

### EC2

```xml
<mxCell value="EC2" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#ED7100;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.ec2;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

### Lambda

```xml
<mxCell value="Lambda" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#ED7100;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.lambda;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

### ECS

```xml
<mxCell value="ECS" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#ED7100;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.ecs;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

### Fargate

```xml
<mxCell value="Fargate" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#ED7100;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.fargate;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

***

## Storage

### S3

```xml
<mxCell value="S3" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#7AA116;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.s3;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

### EBS

```xml
<mxCell value="EBS" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#7AA116;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.elastic_block_store;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

### EFS

```xml
<mxCell value="EFS" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#7AA116;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.elastic_file_system;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

***

## Database

### RDS

```xml
<mxCell value="RDS" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#C925D1;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.rds;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

### Aurora

```xml
<mxCell value="Aurora" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#C925D1;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.aurora;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

### DynamoDB

```xml
<mxCell value="DynamoDB" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#C925D1;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.dynamodb;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

### ElastiCache

```xml
<mxCell value="ElastiCache" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#C925D1;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.elasticache;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

***

## Networking

### VPC

```xml
<mxCell value="VPC" style="sketch=0;outlineConnect=0;gradientColor=none;html=1;whiteSpace=wrap;fontSize=12;fontStyle=0;shape=mxgraph.aws4.group;grIcon=mxgraph.aws4.group_vpc;strokeColor=#879196;fillColor=none;verticalAlign=top;align=left;spacingLeft=30;dashed=0;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="400" height="300" as="geometry"/>
</mxCell>
```

### Subnet (Public)

```xml
<mxCell value="Public Subnet" style="sketch=0;outlineConnect=0;gradientColor=none;html=1;whiteSpace=wrap;fontSize=12;fontStyle=0;shape=mxgraph.aws4.group;grIcon=mxgraph.aws4.group_security_group;grStroke=0;strokeColor=#7AA116;fillColor=#E9F3E6;verticalAlign=top;align=left;spacingLeft=30;dashed=0;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="120" y="140" width="160" height="120" as="geometry"/>
</mxCell>
```

### Subnet (Private)

```xml
<mxCell value="Private Subnet" style="sketch=0;outlineConnect=0;gradientColor=none;html=1;whiteSpace=wrap;fontSize=12;fontStyle=0;shape=mxgraph.aws4.group;grIcon=mxgraph.aws4.group_security_group;grStroke=0;strokeColor=#147EBA;fillColor=#E6F2F8;verticalAlign=top;align=left;spacingLeft=30;dashed=0;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="120" y="280" width="160" height="120" as="geometry"/>
</mxCell>
```

### ALB (Application Load Balancer)

```xml
<mxCell value="ALB" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#8C4FFF;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.application_load_balancer;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

### CloudFront

```xml
<mxCell value="CloudFront" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#8C4FFF;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.cloudfront;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

### API Gateway

```xml
<mxCell value="API Gateway" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#E7157B;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.api_gateway;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

### Route 53

```xml
<mxCell value="Route 53" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#8C4FFF;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.route_53;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

***

## Application Integration

### SQS

```xml
<mxCell value="SQS" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#E7157B;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.sqs;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

### SNS

```xml
<mxCell value="SNS" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#E7157B;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.sns;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

### EventBridge

```xml
<mxCell value="EventBridge" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#E7157B;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.eventbridge;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

### Step Functions

```xml
<mxCell value="Step Functions" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#E7157B;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.step_functions;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

***

## Security

### IAM

```xml
<mxCell value="IAM" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#DD344C;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.identity_and_access_management;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

### Cognito

```xml
<mxCell value="Cognito" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#DD344C;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.cognito;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

### Secrets Manager

```xml
<mxCell value="Secrets Manager" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#DD344C;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.secrets_manager;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

***

## Management

### CloudWatch

```xml
<mxCell value="CloudWatch" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#E7157B;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.cloudwatch_2;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

### CloudFormation

```xml
<mxCell value="CloudFormation" style="sketch=0;points=[[0,0,0],[0.25,0,0],[0.5,0,0],[0.75,0,0],[1,0,0],[0,1,0],[0.25,1,0],[0.5,1,0],[0.75,1,0],[1,1,0],[0,0.25,0],[0,0.5,0],[0,0.75,0],[1,0.25,0],[1,0.5,0],[1,0.75,0]];outlineConnect=0;fontColor=#232F3E;fillColor=#E7157B;strokeColor=#ffffff;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;shape=mxgraph.aws4.resourceIcon;resIcon=mxgraph.aws4.cloudformation;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

***

## 外部アクター

### User

```xml
<mxCell value="User" style="sketch=0;outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#232F3D;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.user;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

### Users

```xml
<mxCell value="Users" style="sketch=0;outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#232F3D;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.users;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

### Internet

```xml
<mxCell value="Internet" style="sketch=0;outlineConnect=0;fontColor=#232F3E;gradientColor=none;fillColor=#232F3D;strokeColor=none;dashed=0;verticalLabelPosition=bottom;verticalAlign=top;align=center;html=1;fontSize=12;fontStyle=0;aspect=fixed;pointerEvents=1;shape=mxgraph.aws4.internet_alt2;fontFamily=Hiragino Sans;" vertex="1" parent="1">
  <mxGeometry x="100" y="100" width="78" height="78" as="geometry"/>
</mxCell>
```

***

## AWS色カテゴリ

| カテゴリ            | fillColor |
| --------------- | --------- |
| Compute         | #ED7100   |
| Storage         | #7AA116   |
| Database        | #C925D1   |
| Networking      | #8C4FFF   |
| App Integration | #E7157B   |
| Security        | #DD344C   |
| General         | #232F3D   |

***

## 注意事項

1. **フォント設定**: 各要素に `fontFamily=Hiragino Sans` を追加
2. **サイズ**: 標準は78x78px、小さくする場合は48x48px
3. **ラベル位置**: `verticalLabelPosition=bottom` でアイコン下にラベル配置
4. **アスペクト比**: `aspect=fixed` で比率を維持
