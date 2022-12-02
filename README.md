# Infrastructure
- Create Virtual Private Cloud (VPC)
- Create subnets in your VPC. create 3 subnets, each in a different availability zone in the same region in the same VPC.
- Create an Internet Gateway resource and attach the Internet Gateway to the VPC.
- Create a public route table Attach all subnets created to the route table.
- Create a public route in the public route table created above with destination CIDR block 0.0.0.0/0 and internet gateway created above as the target.
- Assignment 7 changes to add cloud watch agent policy to the IAM Role
- Assignment 8 changes to implement AWS SNS, Lambda function and DynamoDB resources.

# AWS CLI

## AWS Profile

aws configure --profile devuser

aws configure --profile demouser

## AWS CLOUDFORMATION COMMANDS

**Creating Stack**
```
aws cloudformation --profile devuser create-stack --stack-name ____ --template-body file://csye6225-infra.yml
aws cloudformation --profile devuser create-stack --stack-name ____ --template-body file://csye6225-infra.yml --parameters ParameterKey=AMI,ParameterValue="ami-value" --capabilities CAPABILITY_NAMED_IAM
aws cloudformation create-stack --stack-name ____ --template-body file://csye6225-infra.yml --profile demouser --parameters ParameterKey=AMI,ParameterValue="ami-value" ParameterKey=Subdomain,ParameterValue="demo" --capabilities CAPABILITY_NAMED_IAM
```

**Update Stack**
```
aws cloudformation --profile devuser update-stack --stack-name "  " --template-body file://csye6225-infra.yml
```

**Delete Stack**
```
aws cloudformation --profile devuser delete-stack --stack-name "  "
```

**Delete S3 bucket**
```
aws --profile devuser s3 rm s3://bucketname --recursive
```

**Import Certificate**
```
aws acm import-certificate --certificate fileb://Certificate.pem \

      --certificate-chain fileb://CertificateChain.pem \

      --private-key fileb://PrivateKey.pem
```