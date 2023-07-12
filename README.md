# aws-project

## Create VPC

<img width="834" alt="Screenshot 2023-07-12 at 2 55 34 PM" src="https://github.com/bastien707/aws-project/assets/73294817/831c99b3-f97e-48b4-bf92-d6578a43caf9">

<img width="1136" alt="Screenshot 2023-07-12 at 2 56 22 PM" src="https://github.com/bastien707/aws-project/assets/73294817/6ae0e386-bad3-4f50-bcad-d31f78765918">

## Create public subnet

<img width="1136" alt="Screenshot 2023-07-12 at 3 03 28 PM" src="https://github.com/bastien707/aws-project/assets/73294817/25e42f88-993e-4e45-9cf6-a827e1c1915e">

### Set public subnet ipv4
<img width="1140" alt="Screenshot 2023-07-12 at 3 42 46 PM" src="https://github.com/bastien707/aws-project/assets/73294817/f4fce5fc-75f7-439e-a799-5517f7cbf3fe">


### Allow inbound http
<img width="1108" alt="Screenshot 2023-07-12 at 3 29 46 PM" src="https://github.com/bastien707/aws-project/assets/73294817/c2adbd76-e0c3-407d-8a83-ceb3c1ccb5eb">

## Create Internet gateaways

<img width="1134" alt="Screenshot 2023-07-12 at 3 07 09 PM" src="https://github.com/bastien707/aws-project/assets/73294817/74d7efdd-48c7-4a0e-9baf-b283055ccd3a">

### Adding rule
<img width="1080" alt="Screenshot 2023-07-12 at 3 08 56 PM" src="https://github.com/bastien707/aws-project/assets/73294817/4fc284a3-1e47-474a-a883-d9dda39293b0">

## Cloud 9 EC2 instance

<img width="1407" alt="Screenshot 2023-07-12 at 3 16 00 PM" src="https://github.com/bastien707/aws-project/assets/73294817/27c8701c-ccee-41fe-8063-ee1db9ea090a">

### EC2
<img width="1166" alt="Screenshot 2023-07-12 at 4 07 40 PM" src="https://github.com/bastien707/aws-project/assets/73294817/fa4f2092-1413-4548-8e72-45e493d5eb76">

### Inbound rules for EC2
Ping + http
<img width="1161" alt="Screenshot 2023-07-12 at 6 54 01 PM" src="https://github.com/bastien707/aws-project/assets/73294817/ecdfc66a-4c9d-4c1f-826c-0803cc596fc1">

## Create private subnet

<img width="1135" alt="Screenshot 2023-07-12 at 3 22 43 PM" src="https://github.com/bastien707/aws-project/assets/73294817/cd7aa5d0-522b-402c-806d-6e6213a28d1c">

## Create NAT gateaways

<img width="1133" alt="Screenshot 2023-07-12 at 3 33 52 PM" src="https://github.com/bastien707/aws-project/assets/73294817/869d55e3-6ce5-45e3-b110-40a3662d3d99">

## Create private route table

<img width="1132" alt="Screenshot 2023-07-12 at 3 37 29 PM" src="https://github.com/bastien707/aws-project/assets/73294817/c72c5aa8-f42f-4520-a2f7-b22e8357604f">

## Editing routes
<img width="1076" alt="Screenshot 2023-07-12 at 3 38 55 PM" src="https://github.com/bastien707/aws-project/assets/73294817/358fbd2b-31cf-4642-9735-c0621ea8d397">

## Create security group for private DB instance
<img width="1324" alt="Screenshot 2023-07-12 at 4 46 31 PM" src="https://github.com/bastien707/aws-project/assets/73294817/dd6ee555-34a3-412a-8cc4-9dd585fbac1b">

## Create RDS database

<img width="1103" alt="Screenshot 2023-07-12 at 5 34 50 PM" src="https://github.com/bastien707/aws-project/assets/73294817/238d063e-e279-4e0f-be1e-356eeb1c5a15">

## Install project into EC2 instance

<img width="826" alt="Screenshot 2023-07-12 at 6 56 33 PM" src="https://github.com/bastien707/aws-project/assets/73294817/cab871f1-b9ed-4b7d-a4c4-7a304e669c11">

## configure parameter store
<img width="1291" alt="Screenshot 2023-07-12 at 7 40 51 PM" src="https://github.com/bastien707/aws-project/assets/73294817/3ce2c00e-aa28-49bd-ba61-95eb65ac909e">

## Website initialization

<img width="1413" alt="Screenshot 2023-07-12 at 5 56 02 PM" src="https://github.com/bastien707/aws-project/assets/73294817/93ed8bd0-ad88-4a6f-b1b3-12660bf17774">

## Connection to the database from Cloud9

<img width="1132" alt="Screenshot 2023-07-12 at 6 21 45 PM" src="https://github.com/bastien707/aws-project/assets/73294817/d6574bbc-86d7-4c19-b9e8-bde494040bd1">

## Cannot connect to database from another host which is normal for security reasons

<img width="990" alt="Screenshot 2023-07-12 at 6 32 56 PM" src="https://github.com/bastien707/aws-project/assets/73294817/c251a4b1-a64a-414c-9996-13bcccc68d27">

## Select sample datas in Cloud9

<img width="1138" alt="Screenshot 2023-07-12 at 7 20 54 PM" src="https://github.com/bastien707/aws-project/assets/73294817/4315e1af-f673-4121-a131-5d8e7fa9f9dc">

## IAM Role
### Create role with read only access ssm (least privilege)
<img width="1036" alt="Screenshot 2023-07-12 at 7 53 19 PM" src="https://github.com/bastien707/aws-project/assets/73294817/5f53e919-f144-494a-9ad7-d96123b58f63">

### Attach IAM role
<img width="845" alt="Screenshot 2023-07-12 at 7 55 41 PM" src="https://github.com/bastien707/aws-project/assets/73294817/2c87fe5b-ff4b-4306-aa0d-0381e0ba8320">

## Query is working, we are legend !
<img width="1414" alt="Screenshot 2023-07-12 at 7 47 23 PM" src="https://github.com/bastien707/aws-project/assets/73294817/d30fd4d1-a951-47b0-914b-ac2d53e9796d">





