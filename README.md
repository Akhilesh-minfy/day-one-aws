# DAY-One-AWS
## Key Value pair
- create a key value pair with name "Day-One-Akhilesh-KP"

## VPC
- create a vpc only with name "Day-One-Akhilesh-VPC"
![Screenshot (13)](https://github.com/user-attachments/assets/3e550ea1-1e31-4fa1-87a2-a1139f59098b)

## Internet gateway
- create a Internet gateway with name "Day-One-Akhilesh-IG"
- then attach it to the vpc 
![Screenshot (15)](https://github.com/user-attachments/assets/6c5ec986-3a14-4546-85f3-967f3f89a8cb)
![Screenshot (16)](https://github.com/user-attachments/assets/2f903864-9d05-4e34-8817-5fdd6d7ec244)

## Subnet
- create subnet with name "Day-One-Akhilesh-SB" in the vpc you have created
  ![Screenshot (17)](https://github.com/user-attachments/assets/6681dcf2-97db-4f5c-a487-1e34286d9c00)

## Route table
- create a route table with name "Day-One-Akhilesh-RT" in the vpc you have created
- after creating go to routes -> add routes -> source is 0.0.0.0/0 and target is internet gateway that you have created
- edit the subnets and add this route table to it 
  ![Screenshot (18)](https://github.com/user-attachments/assets/86168eba-c2a0-4eed-aaa5-5b38c2a5bf19)
![Screenshot (19)](https://github.com/user-attachments/assets/4c58f4ca-02a3-4d57-b5cc-494c71664986)

## security group
- create security group in the vpc you created and allow https and http traffic
  ![Screenshot (14)](https://github.com/user-attachments/assets/35543a85-4fbd-4d24-b29a-b8f829d68f64)
## Instance
- create instance with name "Day-One-Akhilesh-EC2"
- use the existing vpc and subnet and enable public ip and upload the code
```bash
  #!/bin/bash
yum update -y
yum install -y httpd
systemctl start httpd
systemctl enable httpd
echo "<h1>Hello World from $(hostname -f)</h1>" > /var/www/html/index.html
```
  
- after configuring everything try to access it with ypur instance ip you sholud get the following ouput
![Screenshot (20)](https://github.com/user-attachments/assets/4110c7cc-8b00-4d3f-96a8-7861f24bdb11)




# take home assignment
- create a key value pair
- create a vpc
- create a Internet gateway
- then attach it to the vpc
- create 2 subnets named public-subnet and private-subnet
- create  routes tables for each subnet or create for public-subnet and use default for private-subnet
- after creating edit the subnet assoiciation and attach it to that respective subnets 
- for the route table of public-subnet go to edit routes -> add routes -> source is 0.0.0.0/0 and target is internet gateway that you have created this makes the public-subnet public 
- create security group in the vpc you created named webapp-sg and allow https and http traffic and ssh also 
- create security group in the vpc you created named database-sg and allow mysql/aurora and put the security group of webapp
- create 2 instances one in public-subnet and one in private subnet named web-server and db-server respectively
  ![Screenshot (21)](https://github.com/user-attachments/assets/a22cdc1c-67a6-4f2a-a87e-92835aff46bb)
  ![Screenshot (22)](https://github.com/user-attachments/assets/8124661b-85cd-4660-80d0-85913727c859)



