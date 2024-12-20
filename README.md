# Docker_project
Deploy html file in Docker container

What is Docker?

It is a software development tool and a virtualization technology that makes it easy to develop, deploy manage application by using container

What is Container?

It refers to a lightweight, standlone, executable package of a piece of software that contains all the libraries, configuration files, dependencies and other necessary parts to operate the application. Eg., Ubuntu +Python +Dependencies

What is Docker Images?

 It is static representation of the app or service and its configuration of the app or service and its configuration and dependencies. It is used to create Docker Containers. It is read-only immutable template that defines contains application binaries and dependencies. Docker Images are stored in the docker Registry.



What is Docker Container Lifecycle?

The Docker container lifecycle is the process of creating, running, stopping, and removing a Docker container:
•	Created: The container is created from a Docker image
•	Running: The container executes the commands in the image
•	Paused: The container's current command is paused
•	Stopped: The container's main process is gracefully shut down
•	Killed or deleted: The container's main processes are abruptly shut down 

  


![image](https://github.com/user-attachments/assets/54f80853-099a-4831-91eb-1d34c8057c06)





Step 1:
	Launch Linux instance

 ![image](https://github.com/user-attachments/assets/262e395c-9d6d-4be7-96db-610489fa6aa3)


	After launch instance connect with putty

 
![image](https://github.com/user-attachments/assets/95b3f9e3-ca9b-488e-b602-d7312ff35886)

 
![image](https://github.com/user-attachments/assets/8a50eecf-81c2-4a6e-9332-ec094f9c6815)


commands:
sudo su
yum update -y
yum install docker

![image](https://github.com/user-attachments/assets/f527b3f0-db89-4e7b-bf94-0f6ba12410e6)

 



service docker status--> to check status of docker
press q to quit
service docker start --> to start docker
service docker status --> it will show active
docker images [to list all docker images available in instance]
search 'docker hub' on google--> search ubuntu and copy the command and paste in putty-->
command-- docker pull ubuntu

vi index.html [for creating index.html]
<h1>Hello from docker</h1>
to quit press ecs+ :wq
cat index.html

 
![image](https://github.com/user-attachments/assets/5d45edce-cf91-4a41-ab02-583698448c4a)

docker images
vi Dockerfile
      FROM ubuntu
      RUN apt update -y
      RUN apt-get install apache2 -y
      COPY index.html /var/www/html	
      EXPOSE 80
      CMD ["apachectl", "-D", "FOREGROUND"]
     
    
 
     


      



 

cat Dockerfile
docker build -t img1:v1 .
docker images
docker run -p 80:80 imageid

![image](https://github.com/user-attachments/assets/95133f5f-4ee5-410b-aed6-a0e564f21806)


 

Now Search ec2 under the services and copy the public IP of instances and paste in new tab.


![image](https://github.com/user-attachments/assets/1619afe7-a8ca-47a2-91d9-2345d841100f)

 






