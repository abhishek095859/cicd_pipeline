# GITHUB WORKFLOW TAKE HOME ASSIGNMENT 
In this assignment we are making a pipeline to automate the running and installation of docker inside our EC2 instance
and also the creating and building image and running the container 
firstly we need to create a docke hub image 
and create a new access token or password 
After this creation of access token we need to create a github repo with " CICD_PIPELINE " 
then upload all files app.js , package.json 
then run the 
# npm init -y 
![Screenshot 2025-06-22 104514](https://github.com/user-attachments/assets/c1bd2305-a93a-48e1-b2f0-1a9bf0b5e6a1)

# npm i express
![Screenshot 2025-06-22 104549](https://github.com/user-attachments/assets/22c7b2a0-f9d8-4fde-8f40-cb10747646b6)

then i have created a main.tf and also variable.tf , output.tf
then execute the terraform commands
terraform init, terrform plan , terraform apply
![Screenshot 2025-06-22 104808](https://github.com/user-attachments/assets/b80da805-1f69-4531-97c5-5c28b13482b6)
![Screenshot 2025-06-22 104911](https://github.com/user-attachments/assets/11be82e5-6a0d-4505-bfe7-0d3488f15e14)
in main.tf 
create a security group which allow port 22 and 3000 in bound traffic and ec2 instance type is t2.micro
then after all running we will see the public ip as "13.127.127.123" 
![Screenshot 2025-06-22 100408](https://github.com/user-attachments/assets/ff2ea267-429e-46ba-aceb-b8bf4f9c3f04)
then ssh into our instance to download docker to run our image via pipeline
# ssh -i Abhishek-kp.pem ec2-user@13.127.127.123
![Screenshot 2025-06-22 100507](https://github.com/user-attachments/assets/bb380428-93f6-4ddd-ace0-c9ef991a4281)
after this add secrets in github repo:
DOCKERHUB_USERNAME
DOCKERHUB_TOKEN
EC2_HOST
EC2_USERNAME
EC2_SSH_KEY
![image](https://github.com/user-attachments/assets/606e1a31-4b29-4bed-99d7-c073fca4d981)
now we can see our pipeline is running 
![Screenshot 2025-06-22 100202](https://github.com/user-attachments/assets/9da86755-c15c-4c0b-a255-6fb3deeedf2c)
then copy the public ip and add the port 3000 to the public ip is runnig or not 
http://13.127.127.123:3000/
![Screenshot 2025-06-22 100332](https://github.com/user-attachments/assets/49086fa0-ba79-4799-b298-71582945ae6b)
then now you can see your docker container in our ec2 machine
to clean up this 
terraform destroy










