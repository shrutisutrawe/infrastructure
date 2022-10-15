# Infrastructure
- Create Virtual Private Cloud (VPC)
- Create subnets in your VPC. create 3 subnets, each in a different availability zone in the same region in the same VPC.
- Create an Internet Gateway resource and attach the Internet Gateway to the VPC.
- Create a public route table Attach all subnets created to the route table.
- Create a public route in the public route table created above with destination CIDR block 0.0.0.0/0 and internet gateway created above as the target.

# AWS CLI

## AWS Profile

aws configure --profile devuser

aws configure --profile demouser

## AWS CLOUDFORMATION COMMANDS

**Creating Stack**
```
aws cloudformation create-stack --stack-name ____ --template-body file://csye6225-infra.yml
```

**Update Stack**
```
aws cloudformation update-stack --stack-name "  " --template-body file://csye6225-infra.yml
```

**Delete Stack**
```
aws cloudformation delete-stack --stack-name "  "
```