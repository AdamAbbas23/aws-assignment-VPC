## Assignment 1 Task
Create a custom VPC with one public and one private subnet, set up the correct routing for internet access, and deploy EC2 instances across them.

## Step 1
Create a VPC on the AWS console

<img width="1670" height="1108" alt="Screenshot 2025-12-16 at 10 26 24" src="https://github.com/user-attachments/assets/983b8fb3-98b0-4591-800c-6b626284b49b" />

## Step 2
Create your public and private subnets within your VPC
Make sure the subnets cidr block don't overlap

<img width="1692" height="1133" alt="Screenshot 2025-12-16 at 10 31 50" src="https://github.com/user-attachments/assets/2c0cbf67-61b5-48a2-b260-2757bccc6664" />

## Step 3
Now we have our VPC and our subnets, we can now move on setting up our architecture up for internet access and this will include our Internet Gateway and our NAT gateway for our Private Subnet. 


<img width="1502" height="579" alt="Screenshot 2025-12-16 at 10 37 12" src="https://github.com/user-attachments/assets/7b8f298d-9fed-456e-b5ac-93a531cd0c23" />

<img width="1641" height="932" alt="Screenshot 2025-12-16 at 10 39 35" src="https://github.com/user-attachments/assets/66c77641-ac4e-466f-bbea-b96558af476b" />

## Step 4
Two EC2 instances will be needed, one for public subnet and one for the private subnet.
I will use basic configuration for these EC2s. For the public EC2, we will need to enable auto-assign a public ip so the internet can reach this instance using the public ip.
Whilst creating these instances also add the security groups for inbound and outbound traffic for these EC2 instances.

## Step 5
Attach the Internet Gateway to the public EC2 instance as we want this to have direct access and for our Private EC2 - we want to keep inbound connections protected so we will attach this to the NAT gateway (NAT gateway resides in public subnet because this needs to access the internet hence why it lives in the public subnet)

## Step 6 
Route tables will be needed for public and private traffic. Public route table associated with Internet Gateway, whilst Private to NAT gateway. Route tables needed to tell public and private traffic where to go in their respective route tables.
<img width="1462" height="746" alt="Screenshot 2025-12-16 at 11 02 02" src="https://github.com/user-attachments/assets/4dfc4f28-320a-4123-a388-bd6594cc6797" />

<img width="1462" height="628" alt="Screenshot 2025-12-16 at 11 06 10" src="https://github.com/user-attachments/assets/6bfa7086-44d8-4c9b-8da6-a9cd9af1ae97" />

## Step 7

Now, test to see if I can SSH into my public EC2 and your private network should be complete

<img width="1472" height="693" alt="Screenshot 2025-12-17 at 18 16 48" src="https://github.com/user-attachments/assets/b8c42fbe-5718-404c-ba8e-b6a03845b119" />
