# AWS-VPC-WORDPRESS
In this project I created a VPC for my 3 tier web architecture that hosts my wordpress website servers, ALB's and Database.

 </a>
<a href="https://github.com/jazminchannel/AWS-WordPress-Website">
  <img align="center" src="https://github-readme-stats-git-masterrstaa-rickstaa.vercel.app/api/pin?username=jazminchannel&repo=AWS-WordPress-Website&title_color=ffffff&icon_color=00ba9d&text_color=ffffff&bg_color=001837&hide_border=true" />  

### The configuration for my VPC includes the following:

1. Go to VPC service in console
2. Go to Create VPC 
    - CIDR 10.0.0.0/16 
3. Go to Create Subnet 
    - Choose your VPC
4. Create public subnet A (For ALB) 
    - CIDR 10.0.1.0/24 
    Us-east-1a 
5. Create public subnet B (For ALB ) 
    - CIDR 10.0.8.0/24 
    - Us-east-1b 
6. Create private subnet A (Web Server) 
    - 10.0.16.0/24 
    - Us-east-1a 
7. Create private subnet B (Webserver) 
    - 10.0.24.0/24 
    - Us-east-1b 
8. I did not create a subnet for my database. I configured the database to create a subnet within my VPC upon launch.
9. Enable auto-assign public IPv4 address in Public Subnet A and B 
    - Actions > Edit subnet settings > check Enable auto-assign public IPv4 address 
10. Go to Create Internet Gateway 
    - Create an Internet Gateway 
    - Actions > Attach to VPC 
11. Go to Route Tables 
    - Create two Route tables (one for the public subnets and one for private subnets)  
12.Edit Subnet Associations 
    - Public Route Table 
      * Add route – any IP that isn't local should go through Internet Gateway 
      ![ebsapp](https://github.com/jazminchannel/images/blob/main/GetImage.png)
      * Add all public subnets as explicit subnet associations 
    - Private Route Table 
      * Add all private subnets as explicit subnet associations
 13.Create NAT Gateway for both private subnets
     
      
